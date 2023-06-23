# VBA 기록
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

```javascript
Function macro2(arr1, arr2_1, arr2_2, arr2_3, arr3)
    
'워크시트가 없으면 추가
    For i = LBound(arr1) To UBound(arr1)
        If WorksheetExists(arr1(i)) = False Then
            Worksheets.Add().Name = arr1(i)
        End If
    Next i
    
'워크시트 이동
    Worksheets("미존재2").Move after:=Worksheets("Sheet1")
    Worksheets("미존재3").Move after:=Worksheets("미존재2")
    Worksheets("미존재4").Move after:=Worksheets("미존재3")

'값 입력
    For i = LBound(arr2_1) To UBound(arr2_1)
        Sheets("미존재2").Cells(1, i + 1) = arr2_1(i)
    Next i
    
    For i = LBound(arr2_2) To UBound(arr2_2)
        Sheets("미존재3").Cells(1, i + 1) = arr2_2(i)
    Next i
    
    For i = LBound(arr2_3) To UBound(arr2_3)
        Sheets("미존재4").Cells(1, i + 1) = arr2_3(i)
    Next i
    
    For i = LBound(arr3) To UBound(arr3)
        Sheets("미존재2").Cells(2, i + 1) = arr3(i)
        Sheets("미존재3").Cells(2, i + 1) = arr3(i)
        Sheets("미존재4").Cells(2, i + 1) = arr3(i)
        Sheets("미존재2").Cells(3, i + 1) = arr3(i)
        Sheets("미존재3").Cells(3, i + 1) = arr3(i)
        Sheets("미존재4").Cells(3, i + 1) = arr3(i)
    Next i
    
End Function
```