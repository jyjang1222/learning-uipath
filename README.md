# UIPATH 학습저장소
## 목차
1. 첫 자동화 프로그램 만들기
2. UiPath 패널 설명
3. 자동으로 구글에 날씨 데이터를 수집하여 입을 의상을 추천해주는 프로그램 만들기

## 세팅
### UiPath Extension
- uipath홈에서 도구를 통해 확장기능을 추가 할수있다.
- 확장기능을 설치한 후 해당 브라우저에 접속하면 확장프로그램이 설치된다.
- 확장프로그램이 설치된 후에 설정에 들어가서 '시크릿 모드에서 허용'과 '파일 URL에 대한 액세스 허용'에 체크를 해주어야 한다.

## 액티비티
- Input Dialog: 텍스트 입력창 띄우기 (select,option도 가능)
    - input type(다중선택) 예시: "Seoul;Daegu;" 
- Write Line: 출력창에 로그를 출력 (console.log랑 비슷)
- Use Application/Browser: 외부의 응용프로그램이나 웹브라우저 사용

## 단축키
- ctrl + Y: ctrl+Z 반대
- ctrl + K: 변수 생성