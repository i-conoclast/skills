---
name: testing
description: pytest-based test writing guide. Reference for test-related tasks
---

# Test Guide

## Test Structure

```
tests/
├── conftest.py          # Shared Fixtures
├── unit/                # Unit tests
│   ├── test_models.py
│   └── test_services.py
├── integration/         # Integration tests
│   └── test_api.py
└── e2e/                 # E2E tests
    └── test_workflow.py
```

## Test Markers

```python
@pytest.mark.unit        # Fast unit tests
@pytest.mark.e2e         # Full flow E2E
@pytest.mark.slow        # Slow tests (excluded by default)
@pytest.mark.integration # Integration tests
```

## Run Commands

```bash
pytest                           # All (excluding slow)
pytest -m unit                   # Unit only
pytest -m e2e                    # E2E only
pytest -m integration            # Integration only
pytest --cov=src                 # Coverage
pytest -x --tb=short             # Stop immediately on failure
```

## Unit Test Template

```python
import pytest
from src.services.auth import AuthService

class TestAuthService:
    """AuthService unit tests"""

    @pytest.fixture
    def service(self):
        return AuthService()

    # --- Normal cases ---
    def test_validate_valid_token(self, service):
        result = service.validate("valid-token")
        assert result.is_valid is True

    # --- Exception cases ---
    def test_validate_expired_token(self, service):
        with pytest.raises(TokenExpiredError):
            service.validate("expired-token")

    # --- Parameterized ---
    @pytest.mark.parametrize("token,expected", [
        ("valid", True),
        ("invalid", False),
        ("", False),
    ])
    def test_validate_various_tokens(self, service, token, expected):
        assert service.validate(token).is_valid == expected

    # --- Mock ---
    def test_validate_calls_provider(self, service, mocker):
        mock_provider = mocker.patch.object(service, "provider")
        service.validate("token")
        mock_provider.verify.assert_called_once_with("token")
```

## Fixture Patterns (conftest.py)

```python
import pytest

@pytest.fixture
def sample_data():
    return {"id": 1, "name": "test"}

@pytest.fixture
def db_session():
    session = create_session()
    yield session
    session.rollback()

@pytest.fixture(autouse=True)
def reset_state():
    yield
    # cleanup after each test
```

## Debugging Tips

```bash
pytest -x -vv --tb=long    # Verbose output
pytest --pdb                # Enter debugger
pytest -s                   # stdout output
pytest -k "test_auth"       # Name filter
```

## Workflow

- Write tests for new features: `/impl:test <target>`
- Run unit tests: `/test-unit`
- Run E2E tests: `/test-e2e`
- Full verification: `/verify`
