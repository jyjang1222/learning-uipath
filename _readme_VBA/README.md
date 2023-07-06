# VBA 학습
## 참고 사이트
- https://kukuta.tistory.com/397
- https://mainia.tistory.com/6097

## 시트 존재 확인 후 추가

```vb
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
