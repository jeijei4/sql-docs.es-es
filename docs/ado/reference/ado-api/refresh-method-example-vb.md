---
title: Ejemplo del método Refresh (VB) | Microsoft Docs
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
- Refresh method [ADO], Visual Basic example
ms.assetid: f5375fa1-4711-4f7e-9ba4-54c427f71325
author: rothja
ms.author: jroth
ms.openlocfilehash: 449c6d0da1ddb5915f694020f84a933fa67871e6
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82756545"
---
# <a name="refresh-method-example-vb"></a>Actualización de ejemplo del método (VB)
En este ejemplo se muestra cómo usar el método [Refresh](../../../ado/reference/ado-api/refresh-method-ado.md) para actualizar la colección de [parámetros](../../../ado/reference/ado-api/parameters-collection-ado.md) para un objeto de [comando](../../../ado/reference/ado-api/command-object-ado.md) de procedimiento almacenado.  
  
```vb
'BeginRefreshVB  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
    'To integrate this code  
    'replace the data source and initial catalog values  
    'in the connection strings  
  
    ' connection and recordset variables  
    Dim Cnxn As ADODB.Connection  
    Dim cmdByRoyalty As ADODB.Command  
    Dim rstByRoyalty As ADODB.Recordset  
    Dim rstAuthors As ADODB.Recordset  
    Dim strCnxn As String  
    Dim strSQLAuthors As String  
     ' record variables  
    Dim intRoyalty As Integer  
    Dim strAuthorID As String  
    Dim strRoyalty As String  
  
    ' Open connection  
    Set Cnxn = New ADODB.Connection  
    strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    Cnxn.Open strCnxn  
  
    ' Open a command object for a stored procedure  
    ' with one parameter  
    Set cmdByRoyalty = New ADODB.Command  
    Set cmdByRoyalty.ActiveConnection = Cnxn  
    cmdByRoyalty.CommandText = "byroyalty"  
    cmdByRoyalty.CommandType = adCmdStoredProc  
    cmdByRoyalty.Parameters.Refresh  
  
    ' Get parameter value, execute the command  
    ' and store the results in a recordset  
    strRoyalty = InputBox("Enter royalty:")  
    If strRoyalty = "" Then  
        Err.Raise 1, , "You either didn't enter royalty or canceled the input box. Exit the application"  
    End If  
  
    intRoyalty = Trim(strRoyalty)  
    cmdByRoyalty.Parameters(1) = intRoyalty  
    Set rstByRoyalty = cmdByRoyalty.Execute()  
  
    ' Open the Authors table to get author names for display  
    Set rstAuthors = New ADODB.Recordset  
    strSQLAuthors = "Authors"  
    rstAuthors.Open strSQLAuthors, Cnxn, adOpenForwardOnly, adLockPessimistic, adCmdTable  
  
    ' Print current data in the recordset  
    ' and add author names  
    Debug.Print "Authors with " & intRoyalty & " percent royalty"  
  
    Do Until rstByRoyalty.EOF  
        strAuthorID = rstByRoyalty!au_id  
        Debug.Print "   " & rstByRoyalty!au_id & ", ";  
        rstAuthors.Filter = "au_id = '" & strAuthorID & "'"  
        Debug.Print rstAuthors!au_fname & " "; rstAuthors!au_lname  
        rstByRoyalty.MoveNext  
    Loop  
  
    ' clean up  
    rstByRoyalty.Close  
    rstAuthors.Close  
    Cnxn.Close  
    Set rstByRoyalty = Nothing  
    Set rstAuthors = Nothing  
    Set Cnxn = Nothing  
    Exit Sub  
  
ErrorHandler:  
    ' clean up  
    If Not rstByRoyalty Is Nothing Then  
        If rstByRoyalty.State = adStateOpen Then rstByRoyalty.Close  
    End If  
    Set rstByRoyalty = Nothing  
  
    If Not rstAuthors Is Nothing Then  
        If rstAuthors.State = adStateOpen Then rstAuthors.Close  
    End If  
    Set rstAuthors = Nothing  
  
    If Not Cnxn Is Nothing Then  
        If Cnxn.State = adStateOpen Then Cnxn.Close  
    End If  
    Set Cnxn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
'EndRefreshVB  
```  
  
## <a name="see-also"></a>Consulte también  
 [Command (objeto) (ADO)](../../../ado/reference/ado-api/command-object-ado.md)   
 [Parameters (colección) (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)   
 [Actualizar (método, ADO)](../../../ado/reference/ado-api/refresh-method-ado.md)
