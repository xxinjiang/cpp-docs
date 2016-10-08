---
title: "Function-Call Conversions"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: 7
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# Function-Call Conversions
The type of conversion performed on the arguments in a function call depends on the presence of a function prototype (forward declaration) with declared argument types for the called function.  
  
 If a function prototype is present and includes declared argument types, the compiler performs type checking (see [Functions](../VS_visualcpp/Functions--C-.md)).  
  
 If no function prototype is present, only the usual arithmetic conversions are performed on the arguments in the function call. These conversions are performed independently on each argument in the call. This means that a **float** value is converted to a **double**; a `char` or **short** value is converted to an `int`; and an `unsigned char` or **unsigned short** is converted to an `unsigned int`.  
  
## See Also  
 [Type Conversions](../VS_visualcpp/Type-Conversions--C-.md)