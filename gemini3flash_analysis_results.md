# 프로젝트 분석 보고서: 한봄고등학교 웹 아카이브

이 보고서는 `Archiv_hanbom_h.goesw.kr-publicversion` 프로젝트의 구조, 기술 스택 및 내용을 분석한 결과입니다.

## 1. 프로젝트 개요
이 프로젝트는 **한봄고등학교(Hanbom High School) 공식 웹사이트의 정적 아카이브**입니다. 웹사이트의 특정 시점 상태를 보존하기 위해 미러링 기술을 사용하여 생성된 것으로 보입니다.

## 2. 프로젝트 구조 분석
전체적인 구조는 웹 서버의 파일 시스템을 그대로 복제한 형태를 띄고 있습니다.

- **[README.md](file:///c:/Users/user/Downloads/Archiv_hanbom_h.goesw.kr-publicversion/README.md)**: 프로젝트의 목적과 크레딧(Rheehose, 2026년 2월 28일) 정보를 담고 있습니다.
- **`hanbom_h.goesw.kr/`**: 미러링된 사이트의 루트 디렉토리입니다.
    - **`hanbom-h.goesw.kr/`**: 실제 학교 사이트의 콘텐츠가 포함된 핵심 폴더입니다.
        - **`00_common/`**: 공통 자산(CSS, JS, Fonts, Images)이 저장되어 있습니다. 
        - **`hanbom-h/`**: 사이트의 주요 비즈니스 로직(게시판, 메뉴 등)에 대응하는 정적 HTML 파일들이 저장된 곳입니다.
        - **`upload/`**: 사이트에 게시된 실제 업로드 파일(이미지, 첨부파일 등)이 포함되어 있습니다.
        - **`images/`**, **`css/`**, **[js/](file:///c:/Users/user/Downloads/Archiv_hanbom_h.goesw.kr-publicversion/hanbom_h.goesw.kr/hanbom-h.goesw.kr/00_common/js/common.js)**: 사이트 UI 전용 그래픽 및 스크립트 자산입니다.

## 3. 기술 스택 (Front-end)
이 사이트는 전형적인 한국 교육기관 웹 프레임워크 또는 커스텀 CMS를 기반으로 구축되었습니다.

- **프레임워크/라이브러리**:
    - **jQuery (v3.x)**: DOM 조작 및 인터랙션 구현.
    - **Modernizr (2.6.2)**: 브라우저 기능 감지.
    - **Slick Slider**: 메인 비주얼 및 갤러리 슬라이드 구현.
    - **XEIcon**: 아이콘 폰트 시스템.
- **아카이빙 특징**:
    - **[.do](file:///c:/Users/user/Downloads/Archiv_hanbom_h.goesw.kr-publicversion/hanbom_h.goesw.kr/hanbom-h.goesw.kr/hanbom-h/na/ntt/selectNttList.do) 확장자 유지**: 원래 Java/Spring 기반 서버에서 사용되던 URL 패턴([.do](file:///c:/Users/user/Downloads/Archiv_hanbom_h.goesw.kr-publicversion/hanbom_h.goesw.kr/hanbom-h.goesw.kr/hanbom-h/na/ntt/selectNttList.do))을 그대로 파일 확장자로 사용하고 있습니다. 이는 정적 서버에서도 기존 URL 구조를 유지하기 위함입니다 (예: [selectNttList.do](file:///c:/Users/user/Downloads/Archiv_hanbom_h.goesw.kr-publicversion/hanbom_h.goesw.kr/hanbom-h.goesw.kr/hanbom-h/na/ntt/selectNttList.do)).
    - **웹 접근성 고려**: [common.js](file:///c:/Users/user/Downloads/Archiv_hanbom_h.goesw.kr-publicversion/hanbom_h.goesw.kr/hanbom-h.goesw.kr/00_common/js/common.js) 및 HTML 마크업 상에서 웹 접근성 수정을 위한 코드와 주석이 다수 발견되었습니다.

## 4. 주요 분석 포인트
- **게시판 시스템**: [na/ntt/selectNttList.do](file:///c:/Users/user/Downloads/Archiv_hanbom_h.goesw.kr-publicversion/hanbom_h.goesw.kr/hanbom-h.goesw.kr/hanbom-h/na/ntt/selectNttList.do) 등의 파일을 통해 학교 소식, 공지사항 등이 아카이브되어 있음을 확인했습니다.
- **메뉴 체계**: GNB(Global Navigation Bar)는 `학교소개`, `입학안내`, `학교생활`, `취업/진학`, `학습지원센터`, `커뮤니티` 등으로 구성되어 있습니다.
- **최근 유지보수**: 코드 주석(`240329 메인메뉴 웹접근성 수정`)을 통해 2024년 3월까지 활발하게 유지보수되었던 사이트임을 알 수 있습니다.

## 5. 결론
본 프로젝트는 단순한 파일 모음이 아니라, 학교의 디지털 역사를 보존한 **체계적인 웹 아카이브**입니다. 모든 링크와 자산이 상대 경로로 잘 정리되어 있어, 로컬 환경에서 웹 브라우저를 통해 원본 사이트와 유사한 모습으로 열람이 가능하도록 설계되어 있습니다.
