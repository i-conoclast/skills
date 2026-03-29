---
name: debugging
description: 체계적 디버깅 워크플로우 및 에러 분석 패턴
---

# 디버깅 워크플로우

## 트리거

- `/debug <에러 설명>` 또는 자연어로 디버깅 요청 시
- 테스트 실패 후 분석 요청 시

## 워크플로우

### 1단계: 에러 분석
- 에러 메시지/스택 트레이스 파싱
- 관련 파일 및 라인 식별

### 2단계: 코드 추적
- explore Agent 활용:
  - `explore:analyze-code` - 실패 지점 코드 분석
  - `explore:find-deps` - 관련 의존성 확인
  - `explore:find-impact` - 영향 범위 파악

### 3단계: 영향 분석
- 직접 영향 파일
- 관련 테스트 파일
- 설정 파일 확인

### 4단계: 수정 및 검증
- 수정 코드 제안
- verify Agent로 검증 실행

## 자동 Hook 연동

테스트 실패 시 자동 분석:
- 실패 테스트 파일 식별
- 에러 패턴 분류 (assertion, import, runtime, timeout)
- 관련 코드 자동 탐색

## 에러 패턴 분류

| 패턴 | 키워드 | 조치 |
|------|--------|------|
| Import 에러 | ImportError, ModuleNotFound | 의존성 확인 |
| 타입 에러 | TypeError, AttributeError | 인터페이스 확인 |
| 런타임 에러 | RuntimeError, ValueError | 로직 분석 |
| 테스트 실패 | AssertionError | 기대값 vs 실제값 비교 |
| 타임아웃 | TimeoutError | 성능/무한루프 확인 |
