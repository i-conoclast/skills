---
name: impl-review
description: 구현 품질 리뷰 워크플로우. 코드 레벨 분석 및 개선 제안
---

# 구현 리뷰

## 사용법

```
/impl-review <대상>
/impl-review <대상> --with-research    # 외부 조사 포함
/impl-review <대상> --fix              # 분석 후 refactor 연계
```

## 실행 단계

### Phase 1: 코드 분석 (explore)
- `explore:analyze-code` - 동작 분석
- `explore:find-deps` - 의존성 확인
- `explore:find-duplicates` - 중복 탐지

### Phase 2: 외부 조사 (research) [--with-research]
- `research:search-patterns` - 더 나은 패턴 조사
- `research:search-libs` - 대안 라이브러리 탐색

### Phase 3: 분석 리포트
5가지 관점에서 평가:
- **성능**: 불필요한 연산, 알고리즘 효율
- **가독성**: 명명, 구조, 주석
- **유지보수성**: 결합도, 응집도, 테스트 용이성
- **확장성**: 인터페이스 설계, 변경 용이성
- **보안**: 입력 검증, 인증/인가

심각도 분류:
- 🔴 Critical: 버그, 보안 취약점
- 🟡 Warning: 개선 권장
- 🔵 Info: 참고/스타일

### Phase 4: --fix 시 refactor 연계

### Phase 5: 리포트 저장
- `docs/reports/review/{target}_{YYYY-MM-DD}.md`
