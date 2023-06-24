# VBA 학습
## 참고 사이트
- https://kukuta.tistory.com/397
- https://mainia.tistory.com/6097

## 시트 존재 확인 후 추가
```javascript
Sub AddWorksheet(ByVal WorksheetName As String)

If WorksheetExists(WorksheetName) = False Then
    Worksheets.Add().name = WorksheetName
End If

End Sub


Function WorksheetExists(ByVal WorksheetName As String) As Boolean

On Error Resume Next

WorksheetExists = (Sheets(WorksheetName).name <> "")

On Error GoTo 0

End Function
```

## 3차원 배열의 값을 VBA을 통해 sheet 만들고 데이터 입력
```javascript
Sub macro(MyArray As Variant)

    Dim i As Integer
    
'   시트없으면 생성
    For i = 0 To UBound(MyArray) Step 1
        If WorksheetExists(MyArray(i)(0)) = False Then
            Worksheets.Add().Name = MyArray(i)(0)
        End If
    Next i
    
'   시트 순서에 맞게 이동
    For i = 1 To UBound(MyArray) Step 1
        Worksheets(MyArray(i)(0)).Move after:=Worksheets(MyArray(i - 1)(0))
    Next i
    
'   데이터 입력.
    For i = 0 To UBound(MyArray) Step 1
        Dim j As Integer
'   j = 0 에는 시트명이 있기 때문에 1부터 시작
        For j = 1 To UBound(MyArray(i)) Step 1
            Dim k As Integer
            For k = 0 To UBound(MyArray(i)(j)) Step 1
                Debug.Print i, j, k
                Sheets(MyArray(i)(0)).Cells(j, k + 1) = MyArray(i)(j)(k)
            Next k
        Next j
    Next i
End Sub
```