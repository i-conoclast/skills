# 의존성 분석

코드베이스 내에서 특정 파일/모듈의 의존성을 분석합니다.
내부 의존성, 외부 패키지, 역방향 의존성을 모두 파악합니다.

## 실행할 작업

1. import 문 분석 (Grep + Read)
2. 내부 의존성 추출 (프로젝트 내 모듈)
3. 외부 패키지 추출
4. 역방향 의존성 추적 (이 모듈을 사용하는 곳)
5. 의존성 그래프 생성

## 사용자 입력

$ARGUMENTS

- 파일 경로: `src/services/auth.py`
- 모듈명: `src.services.auth`
- 디렉토리: `src/services/`

## 주의사항

- 상대 import 처리 (from . import ...)
- 순환 의존성 감지
- 외부 패키지는 stdlib vs 3rd-party 구분

## 출력 형식

.claude/templates/explore/find-deps.md 형식
