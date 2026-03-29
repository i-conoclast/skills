# 변경 영향 범위 분석

특정 파일/함수를 수정할 때 영향받는 범위를 분석합니다.

## 실행할 작업

1. find-usage로 직접 영향 파악
2. find-deps로 의존성 그래프 구축
3. 간접 영향 계산 (A -> B -> C 체인)
4. 관련 테스트 파일 찾기
5. 위험도 평가

## 사용자 입력

$ARGUMENTS

- 파일 경로: `src/services/auth.py`
- 함수명: `AuthService.validate`
- 클래스명: `AuthService`

## 주의사항

- 테스트 파일 반드시 포함
- 간접 영향은 2-depth까지만
- 위험도는 영향받는 파일 수 기반

## 출력 형식

.claude/templates/explore/find-impact.md 형식
