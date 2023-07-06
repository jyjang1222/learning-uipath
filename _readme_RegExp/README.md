# 정규식 학습 기록

## 정규식 정보 사이트
- https://regexr.com - 직접 코드를 쳐서 연습 해볼 수 있는 사이트
- https://youtu.be/V_ePeBaQzSc - 생활코딩 정규식 표현 강의
- http://zvon.org/comp/r/tut-Regexp.html#Pages~Contents - 정규식 예시
    - 많이 사용되는 정규표현식 패턴순으로 정리되어 있음

## 예시

```vb
Option Explicit
Option Base 1

Sub howToUse()

    '도구 > 참조 > Microsoft VBScript Regular Expressions 5.5 추가
    '혹은 Set rgx = CreateObject("vbScript.regExp")로 선언
    Dim rgx As Object
    Set rgx = New RegExp
    
    Dim str As String
    
    'rgx.Pattern = "문자열": 문자열을 패턴으로 등록
    
    'rgx.Global = True: 전체 일치 탐색
    'rgx.Global = False: 첫 번째 일치 탐색, Default
    
    'rgx.IgnoreCase = True: 대소문자 구분
    'rgx.IgnoreCase = False: 대소문자 구분하지 않음, Default
    
    'rgx.MultiLine = True: 복수 라인 탐색
    'rgx.MultiLine = False: 한 줄 탐색, Default
    
    'Execute: 일치값들을 배열로 반환
        str = "Hello, World!"
        
        rgx.Global = True
        rgx.Pattern = "." '한 자리 문자
        
        Dim matches As Object
        Set matches = rgx.Execute(str)
        
        Dim match As Variant
        For Each match In matches
            Debug.Print match
        Next
    
    'Replace: 일치값을 특정 문자열로 대체
        str = "주민등록번호: 931209-1234567"
        
        rgx.Global = True
        rgx.Pattern = "\d{6}$" '숫자 여섯 자리, 끝에서
        
        str = rgx.Replace(str, "******")
        Debug.Print str
    
    'Test: 일치값이 있는지 불린값으로 반환
        str = "Hello, World!"
        
        rgx.Pattern = "Hello"
        Debug.Print rgx.Test(str)
        
        rgx.Pattern = "hello"
        Debug.Print rgx.Test(str)
    
End Sub
```