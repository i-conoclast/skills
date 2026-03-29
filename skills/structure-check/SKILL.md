---
name: structure-check
description: 코드 구조 품질 점검. explore 커맨드 조합으로 분석
---

# 구조 품질 점검

## 사용법

```
/structure-check <범위>
/structure-check <범위> --fix    # 분석 후 refactor 연계
```

## 실행 단계

### Step 1: 구조 분석
- `explore:analyze-structure` - 파일 통계, 계층 구조

### Step 2: 중복 탐지
- `explore:find-duplicates` - 중복/유사 코드 탐지

### Step 3: 의존성 분석
- `explore:find-deps` - 순환 의존성, 결합도 확인

### Step 4: 문제 분류
각 문제를 카테고리별로 분류:
- **파일 크기**: 200줄 이상 경고, 300줄 이상 심각
- **함수 복잡도**: 순환 복잡도 10 이상 경고, 15 이상 심각
- **순환 의존성**: 감지 시 심각
- **코드 중복**: 80% 유사도 이상
- **단일 책임 위반**: 파일 내 역할 혼재

### Step 5: 심각도 분류
- 🔴 Critical: 즉시 수정 필요
- 🟡 Warning: 개선 권장
- 🔵 Info: 참고 사항

### Step 6: --fix 시 refactor 연계
- 심각한 이슈에 대해 `/refactor` 실행

### Step 7: 리포트 저장
- `docs/reports/structure-check/{target}_{YYYY-MM-DD}.md`
