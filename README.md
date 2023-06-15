# UiPath 학습저장소

## RPA Challenges
- https://community.robotict.com/c/challenge/9

## UiPath rpa 개발자 코스 - udemy
- https://www.udemy.com/course/complete-uipath-rpa-developer-course/

1. 첫 자동화 프로그램 만들기
2. UiPath 패널 설명
3. 자동으로 구글에 날씨 데이터를 수집하여 입을 의상을 추천해주는 프로그램 만들기
4. 엑셀 파일과 응용 프로그램을 활용해서 자동으로 웹에 데이터를 입력하는 프로그램 만들기

## 빠코의 디비 스토리 - youtube
- https://www.youtube.com/@user-yx5yw3ok2q

1. 기초편
2. 응용편
3. 고급편

## UiPath Extension
- uipath홈에서 도구를 통해 확장기능을 추가 할수있다.
- 확장기능을 설치한 후 해당 브라우저에 접속하면 확장프로그램이 설치된다.
- 확장프로그램이 설치된 후에 설정에 들어가서 '시크릿 모드에서 허용'과 '파일 URL에 대한 액세스 허용'에 체크를 해주어야 한다.

## 패키지 관리
- 디자인 메뉴에서 패키지관리를 통해 플러그인 설치 가능
- 추천
    - UiPath.Excel.Activities
    - UiPath.PDF.Activities

## 연산자
- \ : 몫
- mod : 나머지
- <> : 다른가
- ^ : 제곱

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

## 배열 요소 추가하는 법
### 배열 선언
- new String(){}

### 배열 요소 추가하는 법
- Array.Append(1).ToArray
- 출력할때 : String.join(",")

### 배열에 ""인 아이템을 삭제하는 코드
- strArr_total.Where(Function(s) s <> "").ToArray
- strArr_total = strArr_total.Where(Function(s) s <> "").ToArray

## DataRow 타입
- Add Data Row 액티비티에서 row의 배열이 너무 길때 유용하다.
- 선언방법 : dr_row = DataTable.NewRow
- 참조방법 : dr_row("소속부서"), dr_row(index)

## Dictionary 사용법
### Dictionary 선언 방법
- dict_temp = New Dictionary(of String, String)

## UiElement 변수 사용법에 대해
- https://forum.uipath.com/t/variable-uielement/275353

## UI Selector
- 5초 동안 구성 일시 중지 : F2
- 이미지 선택 모드 : F3
- UI 프레임워크: F4 토글
    - Default : UiPath에서 자체 개발한 라이브러리입니다. 일반적으론 해당 라이브러리를 사용하여 선택 지정
    - AA : 기본 라이브러리에서 선택되지 않고, MFC, VB6 버전과 같이 오래 전 개발된 프로그램의 엘리먼트를 선택 해야할 경우 사용하여 선택 지정
    - UIA : 기본 라이브러리에서 선택되지 않고, WPF와 같이 비교적 최근 도입된 UI 프레임워크 기반의 프로그램의 엘리먼트를 선택해야할 경우 사용하여 선택 지정

## Methods
- ToString : 문자열로 타입변환. 
    - 예) iAge.ToString
    - 숫자에 , 넣기 : Num.ToString("#,##0")
- split : 옵션을 추가할때는 , 로 구분한다. 나누는 기준의 디폴트는 공백이다.
    - split메서드의 옵션을 활용해서 공백마다 나누는 것이 아닌 행마다 나누게 한다. 옵션: Environment.NewLine.ToArray
    - split메서드에 추가 옵션으로 빈문자열일 경우 저장을 하지않도록 할수 있다. 옵션: StringSplitOptions.RemoveEmptyEntries
    - 예) sGetText.split(Environment.NewLine.ToArray, StringSplitOptions.RemoveEmptyEntries)
    - 예) sVar.split, Split(sVariable, " ")
- Contains : 해당 문자열에 명시한 문자열이 있으면 true 없으면 false 반환
    - 예) row.Contains("성명")
- Length : 문자열의 길이나 배열의 길이를 반환
    - 예) sVar.Length, Len(sVar)
- Trim : 양끝의 공백을 제거한다. 
    - 예) "Trim : [" + sVariable.Trim + "]"
- Ltrim : 왼쪽편의 공백을 제거한다.
    - 예) "Ltrim : [" + LTrim(sVariable) + "]"
- Rtrim : 오른쪽편의 공백을 제거한다.
    - 예) "Rtrim : [" + RTrim(sVariable.Trim) + "]"
- Replace : 특정 문자열을 교체한다.
    - 예) "Replace : [" + sVariable.Replace("동해", "서해") + "]"
- Remove : 문자열을 index부터 count만큼 삭제한다. 인덱스는 0부터 시작
    - 예) sVariable.Remove(startIndex, Count)
- Left : 왼쪽에서부터 Length만큼만 반환한다.
    - 예) "Left : [" + Left(sVariable, length) + "]"
- Right : 오른쪽에서부터 Length만큼만 반환한다.
    - 예) "Right : [" + Right(sVariable, 6) + "]"
- Substring : 문자열을 index부터 count만큼만 반환한다. 인덱스는 0부터 시작
    - 예) "Substring : [" + sVariable.Substring(startIndex, count) + "]"
- StartsWith : 특정 문자열로 시작하는지.. true or false 로 반환
- EndsWith : 특정 문자열로 끝나는지.. true or false 로 반환
- Format
- IndexOf
- Environment.NewLine : 개행
- vbCrLf : 개행
- system.Environment.UserName : 사용자 계정 이름 가져오기
- Environment.CurrentDirectory : 현재 프로젝트 디렉토리 가져오기

## 주석 넣기
- Activity 기능에 대한 설명 및 변수 사용에 대해 설명을 주석을 통해 넣을 수 있다.
- Activity 선택 -> 마우스 우클릭 -> 주석 -> 주석 추가 선택

## 단축키
|단축키|설명|
|:---:|:---|
|Ctrl + Shift + N|새로운 빈 프로세스를 생성합니다.|
|Ctrl + Shift + S|현재 열려있는 모든 워크 플로우를 저장합니다.|
|Ctrl + Shift + T|액티비티 검색창 활성화|
|Ctrl + Shift + E|고급 편집기(Expression Editor) 여는 단축키. uipath 액티비티 input창 활성화 시킨 뒤 입력해야함|
|Alt + Enter|고급 편집기(Expression Editor) 닫는 단축키. 확인(OK)|
|Ctrl + Tab|.xaml 파일들 옮겨다닐 수 있음|
|Ctrl + N|새로운 시퀀스 파일 생성|
|Ctrl + O|이전에 만든 워크 플로우를 열 수 있습니다.|
|Ctrl + S|현재 열려있는 워크 플로우를 저장합니다.|
|Ctrl + F|검색 표시줄을 엽니다.|
|Ctrl + D|현재 선택된 액티비티를 무시합니다. (주석처리)|
|Ctrl + E|주석 처리 된 액티비티의 주석을 제거합니다.|
|Ctrl + F5|현재 프로젝트를 실행합니다.|
|Ctrl + F6|현재 열린 .xaml파일을 실행 합니다.|
|Ctrl + C|선택한 활동을 클립 보드에 복사합니다.|
|Ctrl + V|복사 한 활동을 선택된 항목 안에 붙여 넣습니다.|
|Ctrl + K|필요한 활동 유형과 동일한 유형의 변수를 만듭니다.|
|Ctrl + M|필요한 활동 유형과 동일한 유형 의 In 인수를 작성합니다.|
|F2|기록 활동(셀렉터 선택) 중 지연을 추가합니다. (3초)|
|F5|-.xaml 파일을 Main으로 설정 한 상태 에서 현재 프로젝트를 디버깅 모드로 실행합니다 .|
|F6|현재 열린 .xaml파일을 디버깅 모드로 실행 합니다.|
|F9|브레이크 포인트 설정/해제/삭제|

## PDF 데이터 가져오기
- PDF문서의 특정 데이터를 가져 오고 싶다면 배열을 활용해야 한다.
- 예) sGetText.split(Environment.NewLine.ToArray, StringSplitOptions.RemoveEmptyEntries)
1. Read PDF Text를 통해 pdf문서의 데이터를 string으로 가져와서 '출력 > 텍스트'를 통해 string변수에 저장한다.
2. Assign을 통해 pdf 데이터를 저장할 배열을 만든다.
3. 위에서 저장한 pdf문서의 데이터를 split메서드를 활용하여 배열에 개행 문자열로 나누어서 저장한다.
4. split메서드의 옵션을 활용해서 공백마다 나누는 것이 아닌 행마다 나누게 한다. 옵션: Environment.NewLine.ToArray
5. split메서드에 추가 옵션으로 빈문자열일 경우 저장을 하지않도록 할수 있다. 옵션: StringSplitOptions.RemoveEmptyEntries

## SMTP 첨부파일 여러개 넣기
- 예) Directory.GetFiles("C:\Users\" + pcAccountId+ "\Downloads\temp")
- gmail
    - 서버 : "smtp.gmail.com"
    - 포트 : 465

## Get IMAP Mail Message Activity
- 가져온 메일 데이터는 for each문을 돌려서 확인한다.
    - 타이틀 : item.Subject
    - 본문 : item.Body
- gmail
    - 서버 : "imtp.gmail.com"
    - 포트 : 993

## ToString메서드 대신 사용할 수 있는 문자열 메서드
- String.Format("{idx1}{idx2}{idx3}", item1, item2, item3)
- 예) String.Format("{0} : {1}, {2}", name, scoreTotal, scoreTotal / 4)
- 가격에 , 넣기 ToString("#,##0")

## 반올림
- Cint(), Math.round
- 예)
    - 0.5 -> 0
    - 1.5 -> 2
    - 2.5 -> 2
    - 3.5 -> 4
    - 4.5 -> 4
    - 10.5 -> 10

## 외부 워크플로에서 데이터를 처리해서 가져오기
- Invoke Workflow File 사용
- 인수를 활용
- data1 -> in_num -> out_num -> data2

## UiPath 언어 선택, visual basic vs c#
사실 VB냐 C# 이냐는 크게 차이가 없고 둘다 비슷하다.  
하지만 만약, 둘 중 선택을 해야 한다면 VB를 하는 것이 좋다.  
왜냐면 UiPath가 기본언어로 선택한 것이 VB이기 때문이다.  
.NET 기반이라 크게 차이는 없겠지만, 그래도 VB 가 더 잘 호환되어 구동되지 않을까? 생각된다.

## 팁
- 프로젝트 패널에서 프로젝트 이름을 더블클릭하면 해당 폴더가 열린다.
- 크롬에서 auto resume downloads 확장을 설치하면 파일 다운로드가 실패해도 자동 다시 시작
- pc환경이 달라져도 자동화 프로세스가 동작하도록 코드를 작성하자.
- 개발자는 테스트를 할 때 디버그 메뉴에서 실행해보도록 하자
- Navigate To 액티비티 바로 뒤에 delay 1초를 주는 것이 셀렉트가 잘된다.

## 속도 개선
- 노트북은 충전기를 연결해야 성능이 올라간다.
- excel파일을 핸들링할 때 excel scope 액티비티를 쓰는 것을 지양하도록 하자 엑셀 파일을 켜는데 시간이 걸리는데 Workbook 액티비티를 사용하면 엑셀 파일을 켜지 않아도 된다.
- while문은 사용하는 것을 웬만해서 지양하도록 하자
- 시간 걸리는 양 : 액티비티 > 메소드

## 과제 검수 받을때
- 서로 알고 있는 내용을 중점적으로 나만 알고 있는 내용은 상대방이 알아들을 수 있도록 상세히 충분히 설명 
- 개발할 때 목적성을 가져야한다
- 일단 해결이 급한 것은 맞지만 생각을 하면서 작업을 해야 실력이 는다

## 회사 노트북 교체
- 지원받은 노트북이 사용기간이 다돼가서 교체할때는 2주전에 교체 하면 되는데 보안상 교체가 힘들기 때문에 프로젝트 전에는 미리 바꿔달라고 요청

## 오류 해결
- 컴파일에러 : “ " 구별

## 디버그 모드에서 브레이크를 해준 후에 값 확인
- 보기 패널에서 표현식을 작성하면 값을 바로 확인 가능하다 (변수에 넣어서 출력하는 방식은 오래걸림)

## Pdf이미지에서 데이터 추출
- OmniPage OCR
- Digitize Document

## Document Class
- https://docs.uipath.com/activities/other/latest/user-guide/document-class
- 속성
    - Pages : Pages속성을 활용해서 document의 필요한 데이터를 탐색할 수 있다.
        - 예) DocumentVariable.Pages(0).Sections(0).WordGroups(1).Words(0).Text

## 첨부파일 여러개 넣기
- 파일이름에 경로+파일이름을 작성해도 업로드가 가능하다.
- Chr(34) : " 을 활용
- 예:) resultFolderPath + Chr(34) + resultFileName + Chr(34) + Chr(34) + resultFileName2 + Chr(34)
- https://www.youtube.com/watch?v=U-9wYDIAN5Q

## 동시 정렬
### 방법1
- (From x In dt_res.AsEnumerable() Order By convert.ToString(x("끌올여부")) Descending, convert.ToString(x("가격")) Select x).CopyToDataTable()
- (From x In dt.AsEnumerable Order By convert.ToString(x("끌올 여부")) Descending, convert.ToInt32(x("가격").ToString.Replace("원", "").Replace(",","").Replace("가격없음", "0")) Select x).CopyToDataTable
- https://uipath.tistory.com/52
- https://www.youtube.com/watch?v=U-9wYDIAN5Q
### 방법2
- DataView 형식 변수 view 선언
- 예시
    - view = new dataview(dt_res)
    - view.Sort = "가격 desc, 끌올여부 asc"
    - DataTable = view.ToTable

- https://gent.tistory.com/320 - DataView

## 디버그 모드
### 변수에서 오류날시
- 로컬 보기 즉시 중 즉시 패널에서 변수에 오류가 안날 것 같은 값을 다시 할당해서 재실행 할 수 있다.
