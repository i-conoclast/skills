# 함수/클래스 사용처 검색

코드베이스 내에서 특정 함수나 클래스가 어디서 사용되는지 검색합니다.

## 실행할 작업

1. 대상의 import 문 검색 (Grep)
2. 실제 호출 위치 검색 (Grep)
3. 결과를 표 형식으로 정리
4. 사용 패턴 요약

## 사용자 입력

$ARGUMENTS

- 함수명: `UserService` (클래스/함수명)
- 파일 경로: `src/services/user_service.py` (전체 경로)
- 패턴: `UserService.*create` (정규표현식)

## 주의사항

- 대소문자 구분함
- 주석 내 언급은 제외
- 테스트 파일 포함

## 출력 형식

.claude/templates/explore/find-usage.md 형식
