---
title: Ejemplo de la propiedad CacheSize (VC + +) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CacheSize property [ADO], VC++ example
ms.assetid: e0e7b7ba-3943-43cb-a2cd-0e4667187973
author: rothja
ms.author: jroth
ms.openlocfilehash: 68cea9dc78bbb2fa895dc8fb697404e462c1bc07
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82762842"
---
# <a name="cachesize-property-example-vc"></a>Ejemplo de la propiedad CacheSize (VC ++)
En este ejemplo se usa la propiedad [CacheSize](../../../ado/reference/ado-api/cachesize-property-ado.md) para mostrar la diferencia de rendimiento de una operación realizada con y sin una caché de 30 registros.  
  
```  
// CacheSize_Property_Sample.cpp  
// compile with: /EHsc  
#import "msado15.dll" no_namespace rename("EOF", "EndOfFile")  
  
#include <ole2.h>  
#include <stdio.h>  
#include <conio.h>  
#include <winbase.h>  
  
// Function declarations  
inline void TESTHR(HRESULT x) { if FAILED(x) _com_issue_error(x); };  
void CacheSizeX();  
void PrintProviderError(_ConnectionPtr pConnection);  
void PrintComError(_com_error &e);  
  
int main() {  
   if ( FAILED(::CoInitialize(NULL)) )  
      return -1;  
  
   CacheSizeX();  
   ::CoUninitialize();  
}  
  
void CacheSizeX() {  
   // Define ADO object pointers.  Initialize pointers on define.  
   // These are in the ADODB:: namespace  
   _RecordsetPtr pRstRoySched = NULL;  
  
   // Define Other Variables  
   DWORD sngStart;  
   DWORD sngEnd;   
   float sngNoCache;  
   float sngCache;  
   int intLoop = 0;  
   _bstr_t strTemp;  
  
   _bstr_t strCnn("Provider='sqloledb'; Data Source='My_Data_Source'; Initial Catalog='pubs'; Integrated Security='SSPI';");  
  
   try {  
      // Open the RoySched table.  
      TESTHR(pRstRoySched.CreateInstance(__uuidof(Recordset)));  
      pRstRoySched->Open("roysched", strCnn, adOpenForwardOnly, adLockReadOnly, adCmdTable);  
  
      // Enumerate the Recordset object twice and record the elapsed time.  
      sngStart = GetTickCount();  
  
      for ( intLoop = 1 ; intLoop < 2 ; intLoop++ ) {  
         pRstRoySched->MoveFirst();  
  
         while ( !(pRstRoySched->EndOfFile) ) {  
            // Execute a simple operation for the performance test.  
            strTemp = pRstRoySched->Fields->Item["title_id"]->Value;  
            pRstRoySched->MoveNext();  
         }  
      }  
      sngEnd = GetTickCount();  
      sngNoCache = (float)(sngEnd - sngStart) / (float)1000;  
  
      // Cache records in groups of 30 records.  
      pRstRoySched->MoveFirst();  
      pRstRoySched->CacheSize = 30;  
  
      sngStart = GetTickCount();  
  
      // Enumerate the Recordset object twice and record the elapsed time.  
      for ( intLoop = 1 ; intLoop < 2 ; intLoop++ ) {  
         pRstRoySched->MoveFirst();  
         while ( !(pRstRoySched->EndOfFile) ) {  
            // Execute a simple operation for the performance test.  
            strTemp = pRstRoySched->Fields->Item["title_id"]->Value;  
            pRstRoySched->MoveNext();  
         }  
      }  
      sngEnd = GetTickCount();  
      sngCache = (float)(sngEnd - sngStart) / (float)1000;  
  
      // Display performance results.  
      printf("Caching Performance Results:\n");  
      printf("No cache: %6.3f  seconds \n", sngNoCache);  
      printf("30-record cache: %6.3f  seconds", sngCache);  
   }  
   catch(_com_error &e) {  
      // Notify the user of errors if any.  
      _variant_t vtConnect = pRstRoySched->GetActiveConnection();  
  
      // GetActiveConnection returns connect string if connection  
      // is not open, else returns Connection object.  
      switch(vtConnect.vt) {  
      case VT_BSTR:  
         PrintComError(e);  
         break;  
      case VT_DISPATCH:  
         // Pass a connection pointer accessed from the Recordset.  
         PrintProviderError(vtConnect);  
         break;  
      default:  
         printf("Errors occured.");  
         break;  
      }  
   }  
  
   // Clean up objects before exit.  
   if (pRstRoySched)  
      if (pRstRoySched->State == adStateOpen)  
         pRstRoySched->Close();  
}  
  
void PrintProviderError(_ConnectionPtr pConnection) {  
   // Print Provider Errors from Connection object.  
   // pErr is a record object in the Connection's Error collection.  
   ErrorPtr pErr = NULL;  
  
   if ( (pConnection->Errors->Count) > 0 ) {  
      long nCount = pConnection->Errors->Count;  
      // Collection ranges from 0 to nCount -1.  
      for ( long i = 0 ; i < nCount ; i++ ) {  
         pErr = pConnection->Errors->GetItem(i);  
         printf("Error number: %x\t%s", pErr->Number, pErr->Description);  
      }  
   }  
}  
  
void PrintComError(_com_error &e) {  
   _bstr_t bstrSource(e.Source());  
   _bstr_t bstrDescription(e.Description());  
  
   // Print Com errors.    
   printf("Error\n");  
   printf("\tCode = %08lx\n", e.Error());  
   printf("\tCode meaning = %s\n", e.ErrorMessage());  
   printf("\tSource = %s\n", (LPCSTR) bstrSource);  
   printf("\tDescription = %s\n", (LPCSTR) bstrDescription);  
}  
```  
  
## <a name="see-also"></a>Consulte también  
 [CacheSize (propiedad, ADO)](../../../ado/reference/ado-api/cachesize-property-ado.md)   
 [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
