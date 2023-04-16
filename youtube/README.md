# UiPath 학습저장소 - 빠코의 디비 스토리

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
    - 예시: aNameList, sName, iAge, g_global, dYear
- 카멜 표기법을 따른다.

## 데이터 타입
- Object: 모든 데이터 형식을 받을 수 있는 변수이다. 사용되는 변수의 형식을 명확히 모르거나, 하나의 변수에 다양한 형식의 값을 받고자 할 때 사용된다.
- DataTable: 테이블형 복합타입이다. 테이블 내의 다양한 데이터 형식을 담을 수도 있으며, 데이터의 구조적 표현이 가능하다.
- Array of [T]: 열겨된 배열 타입이다. T는 변수 유형인 Type의 약자이며, 다양한 데이터 형식을 선택하여 여러 유형의 배열을 생성할 수 있다.
    - 예시(vb): {"Tom", "Jerry"}

## Activity
- RPA 개발 프로세스는 크게 2가지 유형이며 Sequence, Flow Chart 방식이다.
- Sequence는 작업을 순차적으로 수행할 때 사용하고, Flow Chart는 여러 브랜치나 조건 분기가 있을 경우 사용한다.
- Activity는 드래그앤드롭으로 세팅이 가능하다.
- Activity는 RPA 프로세스를 개발하는데 필요한 기능들이다.
- 모든 Activity들은 속성 값을 가지고 있고, 특성마다 셋팅되는 구성 및 값들이 다르다.

## Activitys
- Assign: 변수 설정. 기본타입: String, 단축키: ctrl+k
- Log Message: 로그 메세지를 남긴다.
- For Each: 주로 Array, DataTable타입 변수들에 사용되며, 하나의 변수가 다수의 정보를 가지고 있을 때, 이들의 해당 값들을 하나씩 참조하는 역할을 한다.
    - 인덱스: 카운터 변수를 선언 가능하며 기본 타입은 Integer이다.
- Build Data Table: 엑셀 데이터 읽기 및 쓰기 시 유용하게 활용 가능하며, 개발 프로젝트 데이터 관리 변수용으로도 많이 활용할 수 있다.
    - 연관 Activity: Add Data Row, For Each Row, Get Row Item, Remove Data Row, Remove Duplicate Rows 등
    - 데이터 테이블: Build Data Table의 값을 가지고 있을 DataTable의 변수를 지정한다.
- For Each Row in Data Table: DataTable DataType의 변수로부터 Row 값들을 하나씩 꺼내오는 역할을 하는 Activity 이다.
    - 데이터 테이블: DataTable의 Row 정보들을 꺼내올 DataTable 변수를 입력 변수로 넣는다.
    - 인덱스: DataTable 변수의 Row 개수를 Count하는 변수를 지정한다. (0부터 시작)

## Methods
- ToString: 문자열로 타입변환. 예시: iAge.ToString

## 단축키
- ctrl + k: 변수 선언
- ctrl + d: 주석 처리 