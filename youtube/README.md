# UiPath 학습저장소 - 빠코의 디비 스토리
## 목차
1. 기초편
2. 응용편
3. 고급편

# 기초편
## 변수 명명 규칙
|접두어|의미|
|:---:|:---|
|<span style="color: red">**a**</span>|Array 배열|
|b|Boolean형 변수|
|By|BYTE형 변수|
|<span style="color: red">**d**</span>|DateTime 날짜형 변수|
|dbl|Double 형 변수 (소수점 포함)|
|f|Float 형 변수 (소수점 포함)|
|<span style="color: red">**g_*</span>*|Global 변수 (전역 변수)|
|h|Handle 형 변수|
|<span style="color: red">**i**</span>|정수 (int)형 변수|
|l|long 형 변수|
|<span style="color: red">**s**</span>|String 문자열|
|<span style="color: red">**dt*</span>*|DataTable 형 변수|
- 변수명의 첫 글자는 변수 타입을 의미하는 접두어를 사용하며 소문자로 표현해준다.
    - 예시: sName, iAge
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

## Methods
- ToString: 문자열로 타입변환. 예시: iAge.ToString