# Git 커밋 생성

Conventional Commits 규칙에 따라 커밋 메시지를 생성하고 커밋합니다.

## 커밋 타입

| 타입 | 설명 | 예시 |
|------|------|------|
| `feat` | 새로운 기능 | feat: add user authentication |
| `fix` | 버그 수정 | fix: resolve timeout handling |
| `refactor` | 리팩토링 | refactor: extract service layer |
| `docs` | 문서 수정 | docs: update API documentation |
| `test` | 테스트 | test: add unit tests for auth |
| `chore` | 빌드/설정 | chore: update lint config |
| `perf` | 성능 개선 | perf: add caching layer |

## 실행할 작업

1. `git status`로 변경 사항 확인
2. 변경 내용 분석하여 적절한 커밋 타입 결정
3. 커밋 메시지 생성
4. 사용자 확인 후 커밋 실행

## 사용자 입력

$ARGUMENTS

- 인자 없음: 변경 사항 분석 후 커밋 메시지 제안
- 타입 지정: `feat: 설명` 형태로 직접 지정
- `--amend`: 마지막 커밋 수정

## 메시지 형식

```
<type>: <subject>

[optional body]

[optional footer]
```

### Subject 규칙
- 50자 이내
- 현재 시제 동사로 시작
- 마침표 없음
