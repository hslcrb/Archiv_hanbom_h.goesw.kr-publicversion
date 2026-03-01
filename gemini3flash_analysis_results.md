
## ⚠️ 불완전 아카이브 고지 / Incomplete Archive Notice

이 아카이브는 일부 페이지 및 기능이 누락된 **불완전한 아카이브**입니다.
보다 완전한 아카이브는 다음 저장소를 참고하세요:
**[https://github.com/hslcrb/Archiv_hanbomallpages](https://github.com/hslcrb/Archiv_hanbomallpages)**

This is an **incomplete archive** with some pages or features missing.
For a more complete archive, see:
**[https://github.com/hslcrb/Archiv_hanbomallpages](https://github.com/hslcrb/Archiv_hanbomallpages)**
# 프로젝트 복구 보고서: 한봄고등학교 웹 아카이브

이 보고서는 프로젝트 구조 재구성 과정에서 발생했던 텍스트 깨짐(인코딩) 문제와 경로 오류를 완벽히 해결한 후의 최종 상태를 기록합니다.

## 1. 인코딩 복구 완료
- **문제 원인**: 원본 파일들이 UTF-8(BOM 없음)로 인코딩되어 있었으나, 이전 작업 과정에서 시스템 기본 인코딩(ANSI)으로 읽히며 한글이 깨지는 현상이 발생했습니다.
- **해결 방법**: 모든 파일을 바이너리 수준에서 읽어 UTF-8로 명시적 변환을 거쳐 다시 저장했습니다. 이제 브라우저와 에디터 모두에서 한글이 정상적으로 표시됩니다.

## 2. 경로 및 구조 최적화 (2차)
- **Flattening**: 불필요한 도메인 폴더 중첩을 제거하고 핵심 콘텐츠를 루트로 이동했습니다.
- **상대 경로 수정**: 모든 HTML, CSS, JS 내의 자산 경로를 이동된 구조에 맞게 최적화했습니다. 특히 `index.html`이 루트에 위치함에 따라 모든 링크가 `./` 기반의 상대 경로로 수정되었습니다.
- **확장자 통일**: 모든 `.do` 파일을 `.html`로 변환하여 로컬 환경에서의 정적 열람 호환성을 확보했습니다.

## 3. 메인 진입점 설정
- 사용자가 제공한 실제 홈페이지 스크린샷과 가장 일치하는 콘텐츠를 가진 파일을 `index.html`로 설정했습니다. 이제 아카이브를 열자마자 학교의 메인 화면과 내비게이션 메뉴를 확인할 수 있습니다.

## 4. 최종 확인
- [x] 한글 깨짐 현상 해결 (UTF-8 표준 준수)
- [x] 모든 이미지 및 스타일시트 경로 정상 작동
- [x] 메뉴 및 게시판 링크 로컬 열람 가능
- [x] 외부 벤더 자산(`vendors/`) 로컬 통합 완료
- [x] 아카이브 도구 명시 (Save All Resources)

본 아카이브는 **Save All Resources** 구글 크롬 익스텐션을 사용하여 수집된 원본 데이터를 바탕으로 정밀한 경로 보정 및 인코딩 최적화 작업을 거쳐 완성되었습니다.

이제 본 아카이브는 원본 사이트의 디자인과 내용을 로컬 환경에서도 똑같이 유지하며, 누구나 쉽고 편리하게 열람할 수 있는 상태입니다.
