# UiPath 학습저장소 - 빠코의 디비 스토리

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

## Activitys
### Assign
변수 설정. 기본타입 : String, 단축키 : ctrl+k

### Log Message
로그 메세지를 남긴다.

### For Each
주로 Array, DataTable타입 변수들에 사용되며, 하나의 변수가 다수의 정보를 가지고 있을 때, 이들의 해당 값들을 하나씩 참조하는 역할을 한다.
- 속성
    - TypeArgument : 묶음 변수 내 값들의 변수 Type을 정의한다.
    - Values : 묶음 변수 명을 넣는다.
    - 인덱스 : 묶음 변수의 개수를 카운트 하는 카운터 변수를 선언 가능하며 기본 타입은 Integer이다.

### Build Data Table
엑셀 데이터 읽기 및 쓰기 시 유용하게 활용 가능하며, 개발 프로젝트 데이터 관리 변수용으로도 많이 활용할 수 있다.
- 연관 Activity : Add Data Row, For Each Row, Get Row Item, Remove Data Row, Remove Duplicate Rows 등
- 속성
    - 데이터 테이블 : Build Data Table의 값을 가지고 있을 DataTable의 변수를 지정한다.

### For Each Row in Data Table
DataTable DataType의 변수로부터 Row 값들을 하나씩 꺼내오는 역할을 하는 Activity 이다.
- 예시 :  row("Name").ToString, row(0).ToString
- 속성
    - 데이터 테이블 : DataTable의 Row 정보들을 꺼내올 DataTable 변수를 입력 변수로 넣는다.
    - 인덱스 : DataTable 변수의 Row 개수를 Count하는 변수를 지정한다. (0부터 시작)

### Add Data Row
- DataTable에 Data Row를 추가할 때 사용되는 Activity이다.
- DataTable의 Columns의 개수 만큼에 항목 데이터를 Row로 넣을 수 있으며, 각 칼럼 데이터 형식에 맞게 데이터를 넣어야 한다.
- Row 데이터는 컬럼 순서에 맞게 배열 형식으로 나열하여 넣거나, DataRow 형식으로 Row Item을 넣을 수 있는 방식이다.
- 속성
    - 데이터 행 : DataRow 형식의 Row 전체의 객체 값을 넣을 때 사용한다.
    - 배열 행 : Array 형식으로 컬럼의 생성 순서에 맞게 데이터를 넣는다.
    - 데이터 테이블 : Add Data Row를 통해 데이터 Row를 추가할 Data Table 변수를 선언한다.

### Remove Data Row
- DataTable 에 Data Row를 제거할 때 사용되는 Activity 이다.
- DataRow 형식으로 Row Item을 넣거나 RowIndex를 이용하여 특정 Row를 삭제할 수 있다.
- 속성
    - DataTable: Row를 삭제할 DataTable 입력 변수를 넣는다.
    - Row : DataRow 형식의 삭제할 Row 개체를 넣는다.
    - RowIndex : 삭제할 DataRow의 Row Index 값을 넣는다.

### Update Row Item
- DataTable 에 Data Row의 컬럼 값을 업데이트할 경우 사용되는 Activity 이다.
- DataRow 의 특정 컬럼의 Index 또는 컬럼명을 지정하여 해당 컬럼의 값을 변경할 수 있다.
- 속성
    - Column name : 값을 업데이트할 컬럼 이름 넣기
    - Column number : 값을 업데이트할 컬럼의 인덱스 번호 넣기
    - Row : 컬럼을 업데이트할 Row 개체
    - 값 : 컬럼의 값을 업데이트할 값

### Remove Duplicate Rows
- DataTable 에 Data Row를 삭제할 때 사용되는 Activity 이다.
- DataTable에 동일한 Row 값을 없애고자 할 때 사용되며, 입력 값에 중복 Row 값을 체크할 DataTable을 입력하고, **출력에 DataTable 형식의 변수를 지정해 주면 해당 변수로 중복이 제거된 DataTable 값이 출력**된다. (기존의 dt 덮어쓰기도 가능)
- 속성
    - 입력 > 데이터 테이블 : 중복 제거를 위해 입력하는 DataTable 변수를 입력 값으로 넣는다.
    - 출력 > 데이터 테이블 : 중복 제거 후 출력되는 값을 담을 DataTable Type의 출력 변수를 넣는다.

### Get Row Item
- For Each Row와 잘 쓰이는 Activity이다.
- 속성
    - 행 : for each row에서 쓰인 행의 변수명을 작성
    - 열 : 인덱스나 컬럼명을 작성
    - 값 : 가져온 값을 저장할 변수명 선언

### Copy File/Folder
- 특정 파일을 복사하는 경우 사용되는 Activity 이다.
- 동일한 파일이 존재하는 경우 덮어쓰기 옵션을 통해 덮어쓰기가 가능하다.
- 출력 경로에 반드시 폴더가 존재해야한다.(자동생성x)
- 속성
    - 오류 발생시 계속 진행 : 오류 발생에도 계속 다음 Activity를 수행할 것인지에 대한 옵션 값(True/False)
    - 보낸 사람 : 복사할 원본 파일(경로 + 파일명)
    - 덮어쓰기 : 덮어쓰기 여부 옵션 값
    - 받는 사람 : 복사할 대상 파일(경로 + 파일명)

### Path Exists
- 파일 또는 폴더 존재 여부를 체크하여 True/False 값을 리턴해 준다.
- 체크하고자 하는 Path를 입력하고 존재 여부의 결과 값은 Boolean(True/False) 값으로 리턴 받게 된다.
- 리턴 받은 값으로 다음 로직을 수행 하도록 한다.
- 예) Path Exists 체크 -> If 조건문을 통한 분기 로직 수행
- 속성
    - 경로 : 체크 경로 정보 입력
    - 경로유형 : 파일 또는 폴더
    - 존재 : 존재 여부에 대해 리턴 받을 변수를 지정한다 (Boolean 변수)

### If
- 조건문의 True/False에 따른 분기 로직을 수행한다.
- 조건문의 결과 값이 참인지 거짓인지에(Boolean(True/False)) 따라 분기 로직을 수행하게 된다.
- 속성
    - Condition : 조건 식을 넣는다

### DateTime
- UiPath의 경우 각 언어에 해당하는 다양한 함수를 사용할 수 있어서 DateTime 또한 동일하게 그 사용법을 활용할 수 있다.
- **yyyy** : 년도, **MM** : 월, **dd** : 날짜, **hh** : 12시간 표현, **dddd** : 요일 표현, **HH** : 24시간 표현, **mm** : 분, **ss** : 초, ms : 밀리초
    - 예) yyyy-MM-dd(2021-11-23), hh:mm:ss(10:44:23), HH:mm:ss (22:44:23)

|메소드 형식|설명|
|:---|:---|
|DateTime.Now|현재 시각, 예) 01/29/20 16:45:28|
|DateTime.Now.ToString<br>("yyyy-MM-dd dddd HH:mm:ss")|DateTime String으로 Format하여 출력|
|DateTime.Now.Year<br>DateTime.Now.Month<br>DateTime.Now.Day<br>DateTime.Now.Hour<br>DateTime.Now.Minute<br>DateTime.Now.Second<br>DateTime.Now.Millisecond|DateTime.Now 의 각 항목을 출력|
|Weekday(DateTime.Now)|DateTime.Now 의 요일 숫자 반환(일:1 ~ 토:7)<br>예) Weekday(Now, FirstDayOfWeek.Monday).ToString|
|DateAdd("YYYY", 10, DateTime.Now)|DateTime.Now 항목에 정수만큼 더한 Date 출력<br>첫번째 인자 값 - (년:YYYY, 월:m, 일:d) 기준으로 DateAdd|
|DateDiff("d", DateTime_1, DateTime_2)|DateTime_2 에서 DateTime_1을 뺀 값<br>첫번째 인자 값 - (년:YYYY, 월:m, 일:d) 기준으로 DateDiff 처리되며, 해당 항목의 차가 정수로 출력|

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