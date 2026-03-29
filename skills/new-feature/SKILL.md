---
name: new-feature
description: 새 기능 추가 전체 워크플로우. explore → spec → research → plan → impl → verify
---

# 새 기능 추가 워크플로우

## 사용법

```
/new-feature <기능 설명>
/new-feature <기능 설명> --with-spec
/new-feature <기능 설명> --with-research
/new-feature <기능 설명> --full
```

## 실행 단계

### Step 1: 탐색 (explore)
- explore Agent 스폰:
  - `explore:analyze-structure` - 관련 디렉토리 구조 파악
  - `explore:find-related` - 유사 기능/파일 탐색
  - `explore:analyze-code` - 기존 패턴 분석

### Step 2: 요구사항 정의 (spec) [--with-spec, --full]
- spec Agent 스폰:
  - `spec:define-fr` - 기능 요구사항
  - `spec:define-criteria` - 성공 기준
  - `spec:define-scenarios` - 테스트 시나리오
- **승인 게이트**: 사용자 확인 후 진행

### Step 3: 조사 (research) [--with-research, --full]
- research Agent 스폰:
  - `research:search-libs` - 관련 라이브러리
  - `research:search-patterns` - 적용 가능한 패턴
  - `research:compare` - 옵션 비교 (필요시)

### Step 4: 계획 (plan)
- plan Agent 스폰:
  - `plan:design` - 설계
  - `plan:breakdown` - 태스크 분해
  - `plan:estimate` - 위험도 평가
  - `plan:files` - 파일 목록
- **승인 게이트**: 사용자 확인 후 진행

### Step 5: 구현 (impl)
- impl Agent 스폰:
  - `impl:create` / `impl:modify` - 코드 구현
  - `impl:test` - 테스트 작성

### Step 6: 검증 (verify)
- verify Agent 스폰:
  - lint + unit test + e2e test

### Step 7: 리포트 저장
- `docs/reports/new-feature/{feature}_{YYYY-MM-DD}.md`

## 실행 모드

| 모드 | 단계 | 트리거 |
|------|------|--------|
| basic | explore → plan → impl → verify | 기본 |
| --with-spec | + spec | 요구사항 정의 필요 시 |
| --with-research | + research | 기술 조사 필요 시 |
| --full | 전체 7단계 | 복잡한 기능 |
