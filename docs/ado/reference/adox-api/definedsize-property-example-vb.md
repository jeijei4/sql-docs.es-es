---
title: Ejemplo de la propiedad DefinedSize (VB) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- DefinedSize property [ADOX], Visual Basic example
ms.assetid: 4dda2239-7ab5-4729-9c63-eb530803f7d9
author: rothja
ms.author: jroth
ms.openlocfilehash: 09e65fec85fd224df64ce7cc7fdb5166e67897e8
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82759191"
---
# <a name="definedsize-property-example-vb"></a>Ejemplo de propiedad DefinedSize (VB)
En este ejemplo se muestra la propiedad [DefinedSize](../../../ado/reference/adox-api/definedsize-property-adox.md) de una [columna](../../../ado/reference/adox-api/column-object-adox.md). El código redefinirá el tamaño de la columna FirstName de la tabla **Employees** de la base de datos *Northwind* . A continuación, se muestra el cambio en los valores del [campo](../../../ado/reference/ado-api/field-object.md) FirstName de un [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) basado en la tabla **Employees** . Tenga en cuenta que, de forma predeterminada, el campo FirstName se rellena con espacios después de volver a definir la propiedad **DefinedSize** .  
  
```  
' BeginDefinedSizeVB  
Public Sub Main()  
    On Error GoTo DefinedSizeXError  
  
    Dim rstEmployees As ADODB.Recordset  
    Dim catNorthwind As New ADOX.Catalog  
    Dim colFirstName As ADOX.Column  
    Dim colNewFirstName As New ADOX.Column  
    Dim aryFirstName() As String  
    Dim i As Integer  
    Dim strCnn As String  
  
    strCnn = "Provider='Microsoft.Jet.OLEDB.4.0';" & _  
             "Data Source='Northwind.mdb';"  
  
    ' Open a Recordset for the Employees table.  
    Set rstEmployees = New ADODB.Recordset  
    rstEmployees.Open "Employees", strCnn, adOpenKeyset, , adCmdTable  
    ReDim aryFirstName(rstEmployees.RecordCount)  
  
    ' Open a Catalog for the Northwind database,  
    ' using same connection as rstEmployees  
    Set catNorthwind.ActiveConnection = rstEmployees.ActiveConnection  
  
    ' Loop through the recordset displaying the contents  
    ' of the FirstName field, the field's defined size,  
    ' and its actual size.  
    ' Also store FirstName values in aryFirstName array.  
    rstEmployees.MoveFirst  
    Debug.Print " "  
    Debug.Print "Original Defined Size and Actual Size"  
    i = 0  
    Do Until rstEmployees.EOF  
        Debug.Print "Employee name: " & rstEmployees!FirstName & _  
            " " & rstEmployees!LastName  
        Debug.Print "    FirstName Defined size: " _  
            & rstEmployees!FirstName.DefinedSize  
        Debug.Print "    FirstName Actual size: " & _  
            rstEmployees!FirstName.ActualSize  
            If Not rstEmployees!FirstName = Null Then  
                aryFirstName(i) = rstEmployees!FirstName  
            End If  
        rstEmployees.MoveNext  
        i = i + 1  
    Loop  
    rstEmployees.Close  
  
    ' Redefine the DefinedSize of FirstName in the catalog  
    Set colFirstName = catNorthwind.Tables("Employees").Columns("FirstName")  
    colNewFirstName.Name = colFirstName.Name  
    colNewFirstName.Type = colFirstName.Type  
    colNewFirstName.DefinedSize = colFirstName.DefinedSize + 1  
  
    ' Append new FirstName column to catalog  
    catNorthwind.Tables("Employees").Columns.Delete colFirstName.Name  
    catNorthwind.Tables("Employees").Columns.Append colNewFirstName  
  
    ' Open Employee table in Recordset for updating  
    rstEmployees.Open "Employees", catNorthwind.ActiveConnection, _  
        adOpenKeyset, adLockOptimistic, adCmdTable  
  
    ' Loop through the recordset displaying the contents  
    ' of the FirstName field, the field's defined size,  
    ' and its actual size.  
    ' Also restore FirstName values from aryFirstName.  
    rstEmployees.MoveFirst  
    Debug.Print " "  
    Debug.Print "New Defined Size and Actual Size"  
    i = 0  
    Do Until rstEmployees.EOF  
        rstEmployees!FirstName = aryFirstName(i)  
        Debug.Print "Employee name: " & rstEmployees!FirstName & _  
            " " & rstEmployees!LastName  
        Debug.Print "    FirstName Defined size: " _  
            & rstEmployees!FirstName.DefinedSize  
        Debug.Print "    FirstName Actual size: " & _  
            rstEmployees!FirstName.ActualSize  
        rstEmployees.MoveNext  
        i = i + 1  
    Loop  
    rstEmployees.Close  
  
    ' Restore original FirstName column to catalog  
    catNorthwind.Tables("Employees").Columns.Delete colNewFirstName.Name  
    catNorthwind.Tables("Employees").Columns.Append colFirstName  
  
    ' Restore original FirstName values to Employees table  
    rstEmployees.Open "Employees", catNorthwind.ActiveConnection, _  
        adOpenKeyset, adLockOptimistic, adCmdTable  
  
    rstEmployees.MoveFirst  
    i = 0  
    Do Until rstEmployees.EOF  
        rstEmployees!FirstName = aryFirstName(i)  
        rstEmployees.MoveNext  
        i = i + 1  
    Loop  
    rstEmployees.Close  
  
    'Clean up  
    Set catNorthwind = Nothing  
    Set colNewFirstName = Nothing  
    Set colFirstName = Nothing  
    Set rstEmployees = Nothing  
    Exit Sub  
  
DefinedSizeXError:  
    Set catNorthwind = Nothing  
    Set colNewFirstName = Nothing  
    Set colFirstName = Nothing  
  
    If Not rstEmployees Is Nothing Then  
        If rstEmployees.State = adStateOpen Then rstEmployees.Close  
    End If  
    Set rstEmployees = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
  
End Sub  
' EndDefinedSizeVB  
```  
  
## <a name="see-also"></a>Consulte también  
 [Objeto column (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)   
 [DefinedSize (propiedad, ADOX)](../../../ado/reference/adox-api/definedsize-property-adox.md)
