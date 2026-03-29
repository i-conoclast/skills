# 최근 변경 사항 추적

git diff를 기반으로 최근 변경된 파일과 내용을 분석합니다.

## 실행할 작업

1. git status로 변경 파일 목록
2. git diff로 변경 내용 확인
3. 변경 유형 분류 (추가/수정/삭제)
4. 주요 변경 사항 요약

## 사용자 입력

$ARGUMENTS

- 범위: `HEAD` (기본값, unstaged changes)
- 커밋: `HEAD~1..HEAD` (마지막 커밋)
- 브랜치: `main..feature` (브랜치 간 차이)
- 경로: `src/` (특정 경로만)

## 주의사항

- Staged와 unstaged 구분
- 바이너리 파일 제외
- 큰 변경은 요약만 표시

## 출력 형식

.claude/templates/explore/find-changes.md 형식
