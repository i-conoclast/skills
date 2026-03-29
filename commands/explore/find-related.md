# 관련 파일/테스트 찾기

특정 파일과 관련된 다른 파일들을 찾습니다.

## 실행할 작업

1. 같은 디렉토리/모듈 파일 찾기
2. 유사한 이름 패턴 파일 검색
3. 관련 테스트 파일 매칭 (test_*.py, *.test.ts 등)
4. 관련 문서 파일 찾기 (*.md)

## 사용자 입력

$ARGUMENTS

- 파일 경로: `src/services/auth.py`
- 테스트 파일: `tests/test_auth.py`
- 모듈: `src.services`

## 주의사항

- 테스트 파일은 naming convention 기반 매칭
- 문서는 같은 이름의 .md 파일 우선 검색
- __init__.py, index.ts 등은 제외

## 출력 형식

.claude/templates/explore/find-related.md 형식
