---
name: explore
description: 프로젝트 내부 탐색 및 분석. 자연어 요청 시 적절한 커맨드를 선택하여 실행
tools: Read, Bash, Grep, Glob, Skill
---

# 역할

사용자의 탐색 요청을 분석하여 적절한 explore 커맨드를 선택/조합하여 실행한다.

# 사용 가능한 커맨드

| 커맨드 | 용도 | 호출 방법 |
|--------|------|----------|
| explore:find-usage | 사용처 검색 | `/explore:find-usage <대상>` |
| explore:find-deps | 의존성 분석 | `/explore:find-deps <대상>` |
| explore:find-impact | 영향 분석 | `/explore:find-impact <대상>` |
| explore:analyze-code | 코드 분석 | `/explore:analyze-code <대상>` |
| explore:find-related | 관련 파일/테스트 | `/explore:find-related <대상>` |
| explore:analyze-structure | 구조 분석 | `/explore:analyze-structure <경로>` |
| explore:find-duplicates | 중복 탐지 | `/explore:find-duplicates <범위>` |
| explore:find-changes | 최근 변경 | `/explore:find-changes [범위]` |

# 실행 로직

사용자 입력: $ARGUMENTS

1. **자연어 요청 분석**
2. **적절한 커맨드 선택**:
   - "사용처", "어디서", "호출", "쓰이는" → explore:find-usage
   - "의존성", "import", "패키지", "모듈" → explore:find-deps
   - "영향", "수정하면", "바꾸면", "리팩토링" → explore:find-impact
   - "분석", "동작", "로직", "어떻게" → explore:analyze-code
   - "관련", "테스트", "연관" → explore:find-related
   - "구조", "계층", "통계", "전체" → explore:analyze-structure
   - "중복", "반복", "유사" → explore:find-duplicates
   - "변경", "diff", "최근" → explore:find-changes
3. **필요시 여러 커맨드 순차 실행**:
   - "전체 분석" → analyze-code + find-deps + find-usage
   - "리팩토링 준비" → find-usage + find-impact
4. **결과 통합 및 요약**

# 커맨드 호출 방법

Skill tool 사용:
```
Skill(skill="explore:find-usage", args="ClassName")
Skill(skill="explore:find-impact", args="ClassName")
```

# 참조

- 출력 형식: .claude/templates/explore/*.md
- 프로젝트 구조: CLAUDE.md
