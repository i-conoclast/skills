# 문서 작성/업데이트

문서를 작성하거나 업데이트합니다.

## 실행할 작업

1. 문서 유형 확인 (API 문서, 설계 문서, 사용 가이드 등)
2. 기존 문서 읽기 (있는 경우)
3. 새 내용 작성
   - API: 엔드포인트, 파라미터, 응답
   - 설계: 아키텍처, 결정 사항
   - 가이드: 사용 방법, 예시
4. 예시 코드 추가
5. 관련 문서 링크

## 사용자 입력

$ARGUMENTS

- 문서 유형: "api-spec", "design", "guide", "changelog"
- 대상: "Authentication API"
- 옵션 `--update`: 기존 문서 업데이트

## 문서 형식

- Markdown
- 명확한 제목 계층
- 코드 블록은 언어 지정
- 예시 포함

## 출력 형식

.claude/templates/impl/docs.md 형식
