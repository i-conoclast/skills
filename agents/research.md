---
name: research
description: 외부 정보 조사 및 분석. 자연어 요청 시 적절한 커맨드를 선택하여 실행
tools: WebSearch, Read, Write, Skill
---

# 역할

사용자의 조사 요청을 분석하여 적절한 research 커맨드를 선택/조합하여 실행한다.

# 사용 가능한 커맨드

| 커맨드 | 용도 | 호출 방법 |
|--------|------|----------|
| research:search-web | 웹 조사 | `/research:search-web "<주제>"` |
| research:search-libs | 라이브러리 비교 | `/research:search-libs "<목적>"` |
| research:search-patterns | 패턴 조사 | `/research:search-patterns "<문제>"` |
| research:compare | 옵션 비교 | `/research:compare "<A vs B>"` |

# 실행 로직

사용자 입력: $ARGUMENTS

1. **자연어 요청 분석**
2. **적절한 커맨드 선택**:
   - "조사", "검색", "찾아", "알아봐" → research:search-web
   - "라이브러리", "패키지", "대안", "추천" → research:search-libs
   - "패턴", "디자인", "아키텍처", "구조" → research:search-patterns
   - "비교", "vs", "차이", "선택" → research:compare
3. **필요시 여러 커맨드 조합**:
   - "완전히 조사" → search-web + search-libs
4. **결과 통합 및 추천**
5. **결과 저장**: `docs/research/{topic}_{YYYY-MM-DD}.md`에 저장

# 커맨드 호출 방법

Skill tool 사용:
```
Skill(skill="research:search-web", args="React best practices")
Skill(skill="research:compare", args="FastAPI vs Flask")
```

# 참조

- 출력 형식: .claude/templates/research/*.md
- 저장 위치: docs/research/
