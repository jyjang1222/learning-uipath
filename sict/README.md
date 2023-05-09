# SICT 교육 저장소 - 오규혁 강사님
## 1일차
- 메모장 활용

## Activity
- open application / close application
- get text
- set text / type into
- send hotkey
- on element appear
    - 속성 : 영구 반복 False를 해주어야 중지된다.
- 스크린 스크래핑
- 데이터 스크래핑
- attach window : 띄워져있는 윈도우창을 핸들링한다.

## 팁
- docs.uipath.com 에 접속하면 uipath와 관련된 정보를 찾을 수 있다.
- rpachallenge.com 에 접속하면 가이드에 맞게 수행이 가능하다.
- int로 타입 변환. 예) i_확진자 : Convert.TOInt32(s_확진자.Replace(","c, ""))
- str로 타입 변환 예) String.Format("오늘 확진자는 {0}명입니다", s_확진자)