# 구조 분석

디렉토리나 모듈의 구조를 분석합니다.

## 실행할 작업

1. 파일 목록 및 통계 (파일 수, 총 줄 수)
2. 디렉토리 계층 구조 시각화
3. 주요 클래스/함수 목록 (크기, 복잡도)
4. 파일 크기 분포 분석

## 사용자 입력

$ARGUMENTS

- 디렉토리: `src/services/`
- 모듈: `src.models`
- 루트: `.` (전체 프로젝트)

## 주의사항

- 캐시, 빌드 산출물 제외 (__pycache__, node_modules, dist 등)
- tests/ 디렉토리는 별도 집계

## 출력 형식

.claude/templates/explore/analyze-structure.md 형식
