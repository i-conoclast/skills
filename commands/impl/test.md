# 테스트 작성

테스트 코드를 작성합니다.

## 실행할 작업

1. 테스트 대상 분석 (explore:analyze-code 활용)
2. 테스트 케이스 설계
   - 정상 케이스
   - 예외 케이스
   - 엣지 케이스
3. 테스트 파일 생성
4. Fixture 작성 (필요시)
5. Mock 설정 (외부 의존성)
6. 테스트 실행 및 검증

## 사용자 입력

$ARGUMENTS

- 대상: "src/services/auth.py"
- 옵션 `--unit`: 유닛 테스트만
- 옵션 `--e2e`: E2E 테스트만
- 옵션 `--all`: 유닛 + E2E

## 테스트 원칙

- AAA 패턴 (Arrange, Act, Assert)
- 각 테스트는 독립적
- 의미 있는 테스트명 (test_<동작>_<조건>_<결과>)
- Fixture 재사용

## 출력 형식

.claude/templates/impl/test.md 형식
