# UiPath 학습저장소 - 빠코의 디비 스토리

## Activity
- RPA 개발 프로세스는 크게 2가지 유형이며 Sequence, Flow Chart 방식이다.
- Sequence는 작업을 순차적으로 수행할 때 사용하고, Flow Chart는 여러 브랜치나 조건 분기가 있을 경우 사용한다.
- Activity는 드래그앤드롭으로 세팅이 가능하다.
- Activity는 RPA 프로세스를 개발하는데 필요한 기능들이다.
- 모든 Activity들은 속성 값을 가지고 있고, 특성마다 셋팅되는 구성 및 값들이 다르다.

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
|Weekday(DateTime.Now)|DateTime.Now 의 요일 인덱스 반환(일:1 ~ 토:7)<br>예) Weekday(Now, FirstDayOfWeek.Monday(추가옵션)).ToString|
|WeekdayName(DateTime.Now)|예) WeekdayName(Now.DayOfWeek, false, FirstDayOfWeek.Monday)|
|DateAdd("YYYY", 10, DateTime.Now)|DateTime.Now 항목에 정수만큼 더한 Date 출력<br>첫번째 인자 값 - (년:YYYY, 월:m, 일:d) 기준으로 DateAdd|
|DateDiff("d", DateTime_1, DateTime_2)|DateTime_2 에서 DateTime_1을 뺀 값<br>첫번째 인자 값 - (년:YYYY, 월:m, 일:d) 기준으로 DateDiff 처리되며, 해당 항목의 차가 정수로 출력|

- 예시
    - "오늘 날짜 : " + dNow.ToString("yyyy-MM-dd dddd HH:mm:ss")
    - "이번달 : " + Now.Month.ToString
    - "요일 인덱스 : " + Weekday(Now).ToString
    - "다음달1일 : " + DateAdd("m", 1, Now.ToString("yyyy-MM")).ToString("yyyy-MM-dd")
    - "이번달의 마지막일자 : " + DateAdd("d", -1, DateAdd("m", 1, Now.ToString("yyyy-MM"))).ToString("yyyy-MM-dd")
    - "년빼기 : " + DateDiff("YYYY", DateAdd("YYYY", -1, Now).ToString("yyyy-MM-dd"), Now.ToString("yyyy-MM-dd")).ToString
    - "년빼기 : " + DateDiff("YYYY", "2022-04-17", "2023-04-17").ToString

### Excel Process Scope
- Excel 프로세스를 열거나 재사용합니다, "Use Excel File" Activity와 함꼐 Excel 문서를 여는 데 사용됩니다.
- 속성
    - 표시되는 행만 : 체크하면 엑셀 시트에서 숨겨진 데이터는 읽어오지 않는다.
    - 저장 위치 : 읽어온 데이터를 저장할 변수를 정함(DataTable).

### Use Excel File
- 회사에서는 엑셀파일에 문서 보안이 걸려있기 때문에 Use Excel File 과 Read Range Activity들을 통해 데이터 참조를 하는 것이 좋다.
- 버전이 업데이트 되면서 Excel Process Scope Activity 내에서 사용 해야 한다.
- 속성
    - 암호 : 읽기 패스워드. 엑셀 파일에 암호가 있을 때 사용.
    - 암호 편집 : 편집 패스워드. 엑셀 파일에 암호가 있을 때 사용.

### Read Range
- 시트에 있는 데이터를 가져오는 Activity
- 특정 범위의 데이터를 가져올때는 Range() 메서드를 사용해야한다.
- 예) Excel.Sheet("Sheet2").Range("B4:G7"), Excel.Sheet("Sheet1").Range("B9")
- 속성
    - 범위 : 어떤 시트에서 데이터를 읽어올 것인지 정함.

### Write DataTable to Excel
- DataTable에 있는 데이터를 엑셀에 입력하는 Activity
- 속성
    - 추가 : 기존 데이터에 데이터 추가
    - 헤더 제외 : 머릿글 제외

### Check App State
- 내가 의도한대로 응용 프로그램이 정상적으로 동작 했는지 상태를 확인하는 Activity (예외처리를 할때 쓰인다)
- 타겟을 선택한 후 엘리먼트를 선택할 때 F4키를 누르면 엘리먼트의 선택 범위 기준을 바꿀 수 있다.
- '브랜치 전환' 버튼을 눌러서 타겟이 나타날때와 나타나지 않을때의 분기를 선택 가능하다.
- 엘리먼트 선택 범위 (단축키F4)
    - 자동 : AA 보다 선택 범위가 세세하다
    - AA : 자동 보다 선택 범위가 단순해진다
    - UIA : 기본 라이브러리에서 선택되지 않고, WPF와 같이 비교적 최근 도입된 UI 프레임워크 기반의 프로그램의 엘리먼트를 선택해야할 경우 사용하여 선택 지정

### Read Cell Value
- 원래 Read만 가능한 Activity 였지만 업데이트 되면서 Read를 하면서 동시에 Cell에 Write도 가능하게 바뀌었다.

### Write Cell
- Read Cell Value가 Write기능이 없던 때 쓰던 Activity이다.
- 예) Excel.Sheet("Sheet1").Cell("B2")

### Use Application/Browser
- 자동화할 응용 프로그램이나 웹브라우저를 선택하는 Activity
- Click Activity 를 사용하기 위한 필요 조건
- 애플리케이션 경로에는 실행파일 경로가 자동으로 지정된다.
- 애플리케이션 인수가 쓰이는 대표적 인것은 office 제품군이고, 인수를 통해 엑셀파일을 개별적으로 구별한다.
- 보통 엑셀을 가장 많이 사용한다.
- 속성
    - 열기/닫기 : Never(하지않음)
    - 창크기조정 : 창 최소화, 최대화

### Click
- 클릭 이벤트를 사용가능하다. (클릭을 해서 창을 닫을 때 유용)
- 엑셀 정식 인증 알림창을 끄려면 UiPath가 안정화가 덜돼서 버그로 인해 Use Application/Browser Activity내에서 Click이벤트를 만든 후 잘라내기를 이용해서 Check App State로 이동시키고 다시 Use Excel파일 내로 옮겨야 에러가 사라진다.
- 속성
    - Click type : 원클릭, 더블, 마우스업, 마우스다운
    - Mouse button : 마우스 좌클, 마우스 우클

### Get Text
- Application UI의 Text 영역에 값을 읽어 올때 사용
- 타겟을 선택 후 닻 모양의 아이콘인 앵커를 추가적으로 선택할 수 있다.

### 엘리먼트 > 컨트롤 > Set Text
- Application UI의 Text 입력 영역에 Text를 입력 시 사용

### Type Info
- Set Text와 기능이 비슷하고 입력하는 텍스트의 타입과 입력하기 전에 필드 비우기나 입력하기 전에 클릭 같은 기능을 추가로 사용 가능하다.

### Start Process
- 응용프로그램을 실행 가능
- 속성
    - 인수 : 매개변수
    - 작업 디렉터리 : 응용프로그램이 속해 있는 경로

### Kill Process
- 응용프로그램을 닫을때 사용
- 속성
    - 프로세스 : Get Processes Activity를 통해 가져온 프로그램 정보를 입력할때 사용
    - 프로세스 이름 : 응용프로그램 이름

### Get Processes
- 현재 실행되고 있는 모든 응용프로그램의 정보를 변수에 저장

### Delay
- 대기시간 입력
- 딜레이를 사용할 때는 액티비티 타이틀에 시간을 명시 하는 것이 좋다. 예) Delay-3
- 일반적으로 초단위를 사용

### Read PDF Text
- pdf의 텍스트를 가져올때 사용
- 속성
    - 서식 유지 : 데이터를 추출할 때 텍스트가 깨진다면 true/false 바꿔가며 테스트
    - 범위 : 가져올 페이지를 설정 가능하다. 예) "1". 기본값은 "All"
    - 텍스트 : 가져온 텍스트를 저장할 변수 설정

### Try ~ Catch ~ Finally
- 안정적인 코드와 예외 처리를 대응하기 위해 사용되는 Activity 이다.
- Try 부분에 일반적인 로직을 넣고 Catch 부분에는 예외가 발생하였을때의 로직을 넣는다.
- Add new Catch 클릭으로 예외를 추가하고 System.Exception을 선택하면 된다.
- exception.Message를 통해 예외 오류 메세지도 확인이 가능하다.
- Finally는 오류가 발생했든 안했든 실행하는 로직으로 작성해도 되고 작성하지 않아도 된다.

### Trigger Scope
- 다양한 트리거를 정의한다.
- 로그 메세지를 통해 파일 변경 내용 확인이 가능하다.
- 예) "File Change Trigger : " + args.FileChangeInfo.FullPath

### File Change Trigger
- Trigger Scope Activity내에서 사용되는 Activity이다.
- 폴더의 변경 사항이 생기면 발생하는 트리거(동작)
- 폴더 내의 변경 내용을 모니터링하고자 할 때 사용 된다.
- 자동화의 산출물을 체크하여 다음 로직을 진행하고자 할때 사용된다.
- 속성
    - FileNameFilter : 체크할 파일명을 명시한다. 예) "*.xlsx"
    - IncludeSubdirectories : true이면 하위 폴더의 변화 까지도 체크하게 된다.
    - 필터 알림 :
    - 형식 변경 : 변경 내용을 체크할 기준을 변경할 수 있다.

### Find Element
- 지정한 UI 엘리먼트가 화면에 나타났는지 체크
- 속성
    - 시간 제한 : 디폴트 30초

### Terminate Workflow
- Try Catch Activity에서 exception에 넣어서 프로세스를 종료 시킬 때 사용된다.
- 속성
    - Exception : 예외에 대행 정보를 담은 exception변수를 넣는다. (Try Catch Activity에서 exception변수가 생성된다.)
    - Reason : 오류가 발생한 이유에 대해 메세지를 남길때

### Flow Decision
- True / False 로 로직을 나눌 때 사용 한다.
- Condition 부분에 bool변수를 선언한다.

### Flow Switch
- Condition변수에 의해 로직을 나눌 때 사용한다.

### Move Window
- 응용 프로그램의 창 위치를 이동 시킬 때 사용한다.

### Compress/Zip Files
- 파일 및 폴더를 압축하기 위해 사용된다.
- 버티컬바 | 를 통해 여러개의 파일 또는 폴더를 입력할 수 있다.
- 예) "test.zip|test2.zip|F:\Jun\learning\learning-uipath\youtube\기초편\ZipUnZip\templates|F:\Jun\learning\learning-uipath\youtube\기초편\ZipUnZip\tmh"

### Extract/UnZip Files
- 압축된 파일 및 폴더를 해제하기 위해 사용된다.

### Extract Table Data
- 리스트 형이면서 페이징 처리가 된 정보를 추출해 오고자 할 때 사용되는 Acitivity이다.
- **추출된 데이터 정보들은 DataTable 형식으로 추출된다.**
- 상단의 '테이블 추출' 버튼을 통해 추출이 가능하다.