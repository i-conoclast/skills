---
name: testing
description: pytest 기반 테스트 작성 가이드. 테스트 관련 작업 시 참조
---

# 테스트 가이드

## 테스트 구조

```
tests/
├── conftest.py          # 공유 Fixture
├── unit/                # 유닛 테스트
│   ├── test_models.py
│   └── test_services.py
├── integration/         # 통합 테스트
│   └── test_api.py
└── e2e/                 # E2E 테스트
    └── test_workflow.py
```

## 테스트 마커

```python
@pytest.mark.unit        # 빠른 유닛 테스트
@pytest.mark.e2e         # 전체 흐름 E2E
@pytest.mark.slow        # 느린 테스트 (기본 제외)
@pytest.mark.integration # 통합 테스트
```

## 실행 명령

```bash
pytest                           # 전체 (slow 제외)
pytest -m unit                   # 유닛만
pytest -m e2e                    # E2E만
pytest -m integration            # 통합만
pytest --cov=src                 # 커버리지
pytest -x --tb=short             # 실패 시 즉시 중단
```

## 유닛 테스트 템플릿

```python
import pytest
from src.services.auth import AuthService

class TestAuthService:
    """AuthService 유닛 테스트"""

    @pytest.fixture
    def service(self):
        return AuthService()

    # --- 정상 케이스 ---
    def test_validate_valid_token(self, service):
        result = service.validate("valid-token")
        assert result.is_valid is True

    # --- 예외 케이스 ---
    def test_validate_expired_token(self, service):
        with pytest.raises(TokenExpiredError):
            service.validate("expired-token")

    # --- 파라미터화 ---
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

## Fixture 패턴 (conftest.py)

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

## 디버깅 팁

```bash
pytest -x -vv --tb=long    # 상세 출력
pytest --pdb                # 디버거 진입
pytest -s                   # stdout 출력
pytest -k "test_auth"       # 이름 필터
```

## 워크플로우

- 새 기능 테스트 작성: `/impl:test <대상>`
- 유닛 테스트 실행: `/test-unit`
- E2E 테스트 실행: `/test-e2e`
- 전체 검증: `/verify`
