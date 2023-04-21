# UiPath 학습저장소

## uipath rpa 개발자 코스 - udemy
- https://www.udemy.com/course/complete-uipath-rpa-developer-course/

1. 첫 자동화 프로그램 만들기
2. UiPath 패널 설명
3. 자동으로 구글에 날씨 데이터를 수집하여 입을 의상을 추천해주는 프로그램 만들기
4. 엑셀 파일과 응용 프로그램을 활용해서 자동으로 웹에 데이터를 입력하는 프로그램 만들기

## 빠코의 디비 스토리 - youtube
- https://www.youtube.com/@user-yx5yw3ok2q

1. 기초편
- Variable
- For Each
- Build Data Table
- For Each Row in Data Table
- Add Data Row
- Remove Data Row
- Update Row Item
- Remove Duplicate Rows

2. 응용편
3. 고급편


## 변수 명명 규칙
|접두어|의미|
|:---:|:---|
|**a**|Array 배열|
|b|Boolean형 변수|
|By|BYTE형 변수|
|**d**|DateTime 날짜형 변수|
|dbl|Double 형 변수 (소수점 포함)|
|f|Float 형 변수 (소수점 포함)|
|**g_**|Global 변수 (전역 변수)|
|h|Handle 형 변수|
|**i**|정수 (int)형 변수|
|l|long 형 변수|
|**s**|String 문자열|
|**dt**|DataTable 형 변수|
- 변수명의 첫 글자는 변수 타입을 의미하는 접두어를 사용하며 소문자로 표현해준다.
    - 예시 : aNameList, sName, iAge, g_global, dYear
- 카멜 표기법을 따른다.

## 데이터 타입
- Object : 모든 데이터 형식을 받을 수 있는 변수이다. 사용되는 변수의 형식을 명확히 모르거나, 하나의 변수에 다양한 형식의 값을 받고자 할 때 사용된다.
- DataTable : 테이블형 복합타입이다. 테이블 내의 다양한 데이터 형식을 담을 수도 있으며, 데이터의 구조적 표현이 가능하다.
- Array of [T] : 열거된 배열 타입이다. T는 변수 유형인 Type의 약자이며, 다양한 데이터 형식을 선택하여 여러 유형의 배열을 생성할 수 있다.
    - 예시(vb) : {"Tom", "Jerry"}

## Activity
- RPA 개발 프로세스는 크게 2가지 유형이며 Sequence, Flow Chart 방식이다.
- Sequence는 작업을 순차적으로 수행할 때 사용하고, Flow Chart는 여러 브랜치나 조건 분기가 있을 경우 사용한다.
- Activity는 드래그앤드롭으로 세팅이 가능하다.
- Activity는 RPA 프로세스를 개발하는데 필요한 기능들이다.
- 모든 Activity들은 속성 값을 가지고 있고, 특성마다 셋팅되는 구성 및 값들이 다르다.

## Methods
- ToString : 문자열로 타입변환. 예시 : iAge.ToString

## 주석 넣기
- Activity 기능에 대한 설명 및 변수 사용에 대해 설명을 주석을 통해 넣을 수 있다.
- Activity 선택 -> 마우스 우클릭 -> 주석 -> 주석 추가 선택

## 단축키
- ctrl + k : 변수 선언
- ctrl + d : Activity 비활성화
- ctrl + e : Activity 활성화
- shift + f2 : 주석 넣기

## UiPath 언어 선택, visual basic vs c#
사실 VB냐 C# 이냐는 크게 차이가 없고 둘다 비슷하다.  
하지만 만약, 둘 중 선택을 해야 한다면 VB를 하는 것이 좋다.  
왜냐면 UiPath가 기본언어로 선택한 것이 VB이기 때문이다.  
.NET 기반이라 크게 차이는 없겠지만, 그래도 VB 가 더 잘 호환되어 구동되지 않을까? 생각된다.