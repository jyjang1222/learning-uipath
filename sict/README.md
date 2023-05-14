# SICT 교육 저장소

- 교육자료
    - http://naver.me/F1MYsFiv
    - http://naver.me/GSUPzLSe

## Activity
- open application / close application
- get text
- set text / type into : typeinto는 직접 타이핑하는 것 처럼 입력됨.
- send hotkey : 단축키를 입력시킬 때 사용된다.
- on element appear
    - 속성 : 영구 반복 False를 해주어야 중지된다.
- 스크린 스크래핑
- 데이터 스크래핑
- attach window : 띄워져있는 윈도우창을 핸들링한다.
    - 보통 open browser 와 같이 쓰인다.
- switch
- maximize window : open browser와 같이 쓰인다.
- parallel : 병렬적으로 수행 하는 액티비티
- input dialog : 입력폼
- modify date : 날짜 변경
- set to clipboard
- get from clipboard
- repeat number of times : 특정 횟수 만큼 for문을 돌릴 때 사용된다.
- copy sheet
- use gmail
- take screenshot
- save image
- invoke method : 메소드를 호출한다.

## Method
- datetime 메소드 : addDays , addHours

## 패키지
- google workspace : 패키지관리에서 gsuite 검색

## 팁
- docs.uipath.com 에 접속하면 uipath와 관련된 정보를 찾을 수 있다.
- rpachallenge.com 에 접속하면 가이드에 맞게 수행이 가능하다.
- int로 타입 변환. 예) i_확진자 : Convert.TOInt32(s_확진자.Replace(","c, ""))
- str로 타입 변환 예) String.Format("오늘 확진자는 {0}명입니다", s_확진자)
- clipboard.setimage : https://learn.microsoft.com/ko-kr/dotnet/api/system.windows.forms.clipboard.setimage?view=windowsdesktop-7.0
- select편집 에서 불필요한 것들을 체크해제하면 셀렉트가 더 잘된다..

## 9, 10일차 자유과제
- 범위 : 본인이 필요하거나 회사에서 필요할만한 과제 선정
- 파일 : workflow, ppt
- 발표예정..

## 엑셀파일 서식
- **글자는 왼쪽정렬, 숫자는 오른쪽 정렬**
- **숫자는 ,가 들어가게 표현**