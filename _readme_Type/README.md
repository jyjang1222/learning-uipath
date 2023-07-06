# UiPath 학습저장소 - 데이터타입

## 데이터 타입
- Object : 모든 데이터 형식을 받을 수 있는 변수이다. 사용되는 변수의 형식을 명확히 모르거나, 하나의 변수에 다양한 형식의 값을 받고자 할 때 사용된다.
- DataTable : 테이블형 복합타입이다. 테이블 내의 다양한 데이터 형식을 담을 수도 있으며, 데이터의 구조적 표현이 가능하다.
- Array of [T] : 열거된 배열 타입이다. T는 변수 유형인 Type의 약자이며, 다양한 데이터 형식을 선택하여 여러 유형의 배열을 생성할 수 있다.
    - 예시(vb) : {"Tom", "Jerry"}

## 배열 Array
### 배열 선언
- {1, 2, 3}
- new String(){}

### 2차원 배열 선언
- {({1}), ({2}), ({3})}
- new String()(){}

### 배열 요소 추가하는 법
- Array.Append(1).ToArray
- 출력할때 : String.join(",", Array)

### 배열에 ""인 아이템을 삭제하는 코드
- strArr_total.Where(Function(s) s <> "").ToArray
- strArr_total = strArr_total.Where(Function(s) s <> "").ToArray

## 딕셔너리 Dictionary
### 딕셔너리 선언
- dict_temp = New Dictionary(of String, String)
- dict_temp = New Dictionary(of String, Int32)
### 딕셔너리 추가
- dict_temp("key1") = "1", dict_temp("key2") = "2"
- for each -> dict_temp("key"+idx_i.ToString) = idx_i
### 값 불러오기
- for each -> item.Key, item.Value.ToString
- dict_temp("key1").ToString = 1
### 딕셔너리 정렬
- dict_temp.OrderBy(Function(x) x.Key).ToDictionary(Function(y) y.Key,Function(y) y.Value)

## 데이터로우 DataRow
- Add Data Row 액티비티에서 row의 배열이 너무 길때 유용하다.
### 데이터로우 선언
- 선언방법 : dr_row = DataTable.NewRow
### 데이터로우 참조
- 참조방법 : dr_row("소속g부서"), dr_row(index)

## UiElement 변수 사용법에 대해
- https://forum.uipath.com/t/variable-uielement/275353

## 문서 Document Class
- https://docs.uipath.com/activities/other/latest/user-guide/document-class
- 속성
    - Pages : Pages속성을 활용해서 document의 필요한 데이터를 탐색할 수 있다.
        - 예) DocumentVariable.Pages(0).Sections(0).WordGroups(1).Words(0).Text

## 타입 변환
### String To DateTime
- CDate(row("마감일")).ToString("yyyy-MM-dd")
- 2024년08월24일, 2024-08-24 가능, 24년08월24일