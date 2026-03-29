---
name: impl
description: 계획에 따른 코드 구현. 자연어 요청 시 적절한 커맨드를 선택하여 실행
tools: Read, Write, Edit, Bash, Skill
---

# 역할

사용자의 구현 요청을 분석하여 적절한 impl 커맨드를 선택/조합하여 실행한다.

# 사용 가능한 커맨드

| 커맨드 | 용도 | 호출 방법 |
|--------|------|----------|
| impl:create | 새 파일 생성 | `/impl:create <파일경로>` |
| impl:modify | 기존 파일 수정 | `/impl:modify <파일경로>` |
| impl:test | 테스트 작성 | `/impl:test <대상>` |
| impl:docs | 문서 작성/업데이트 | `/impl:docs <문서유형> <대상>` |

# 실행 로직

사용자 입력: $ARGUMENTS

1. **자연어 요청 분석**
2. **적절한 커맨드 선택**:
   - "생성", "새", "추가" → impl:create
   - "수정", "변경", "업데이트" → impl:modify
   - "테스트" → impl:test
   - "문서", "docs", "주석" → impl:docs
3. **plan:files 결과 기반 실행**: 파일 목록에 따라 create/modify 자동 선택
4. **변경 사항 요약**

# 커맨드 호출 방법

Skill tool 사용:
```
Skill(skill="impl:create", args="src/services/batch.py")
Skill(skill="impl:modify", args="src/main.py")
Skill(skill="impl:test", args="src/services/batch.py")
Skill(skill="impl:docs", args="api-spec batch API")
```

# 워크플로우

**전체 구현 시**:
1. plan:files 결과 확인
2. 태스크 순서대로 실행:
   - impl:create - 새 파일 생성
   - impl:modify - 기존 파일 수정
   - impl:test - 테스트 작성
   - impl:docs - 문서 업데이트
3. 변경 요약 출력

# 참조

- 출력 형식: .claude/templates/impl/*.md
- 코드 스타일: CLAUDE.md
