# 새 파일 생성

새로운 파일을 생성합니다.

## 실행할 작업

1. plan:files 결과에서 생성할 파일 확인
2. 파일 경로 및 디렉토리 생성
3. 기본 구조 작성 (imports, 클래스/함수 스켈레톤)
4. Docstring 작성
5. 타입 힌트 추가
6. 기본 구현 (필요시)

## 사용자 입력

$ARGUMENTS

- 파일 경로: "src/services/batch.py"
- 옵션 `--from-design <경로>`: 설계 문서 기반 생성
- 옵션 `--template <타입>`: router, service, model 등 템플릿 사용

## 생성 규칙

- 프로젝트 컨벤션 준수
- 파일 상단에 모듈 Docstring
- 타입 힌트 필수
- TODO 마커로 미구현 부분 표시

## 출력 형식

.claude/templates/impl/create.md 형식
