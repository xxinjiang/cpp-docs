---
title: "operator delete (CRT)"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "scalar delete"
  - "operator delete"
ms.assetid: bcd0066a-0022-45f5-af4c-9007c64a6b89
caps.latest.revision: 9
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# operator delete (CRT)
Frees allocated block.  
  
## Syntax  
  
```  
  
      void __cdecl operator delete(  
   void * object  
);  
void __cdecl operator delete(  
   void * object,   
   void * memory  
) throw();  
void __cdecl operator delete(  
   void * object,   
   const std::nothrow_t&  
) throw();  
```  
  
#### Parameters  
 *memory*  
 The memory location being freed.  
  
 *object*  
 A pointer to the object being deleted.  
  
## Remarks  
 This form of **operator delete** is known as scalar delete, in contrast to the vector delete form ([operator delete&#91;&#93;](../crt/operator-delete-crt-.md)).  
  
 **operator delete** frees memory allocated by [operator new](../crt/operator-new--crt-.md).  
  
 The first form of this operator is known as the nonplacement form. The second and third forms of this operator will commonly not be called from code but exist to give the compiler a matching delete to call when a placement new fails.  
  
 The first form of the operator is defined by the compiler and does not require new.h to be included in your program.  
  
 With the exception of throwing or no-throwing behavior, the CRT **operator delete** behaves like [operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md) in the Standard C++ Library.  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|**delete**|\<new.h>|  
  
 For additional compatibility information, see [Compatibility](../crt/compatibility.md) in the Introduction.  
  
## Libraries  
 All versions of the [C run-time libraries](../crt/crt-library-features.md).  
  
## Example  
 See [operator new](../crt/operator-new--crt-.md) for examples of using operator **delete**.  
  
## See Also  
 [Memory Allocation](../crt/memory-allocation.md)