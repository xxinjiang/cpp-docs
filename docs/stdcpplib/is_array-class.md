---
title: "is_array Class"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "is_array"
  - "std.tr1.is_array"
  - "std::tr1::is_array"
  - "std.is_array"
  - "std::is_array"
  - "type_traits/std::is_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_array class [TR1]"
  - "is_array"
ms.assetid: 61fb2201-8de3-4746-9721-617f02df170f
caps.latest.revision: 16
ms.author: "corob"
manager: "ghogen"
translation.priority.mt: 
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
# is_array Class
Tests if type is array.  
  
## Syntax  
  
```
template<class Ty>
struct is_array;
```  
  
#### Parameters  
 `Ty`  
 The type to query.  
  
## Remarks  
 An instance of the type predicate holds true if the type `Ty` is an array type, otherwise it holds false.  
  
## Example  
  
```  
// std_tr1__type_traits__is_array.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_array<trivial> == " << std::boolalpha   
        << std::is_array<trivial>::value << std::endl;   
    std::cout << "is_array<int> == " << std::boolalpha   
        << std::is_array<int>::value << std::endl;   
    std::cout << "is_array<int[5]> == " << std::boolalpha   
        << std::is_array<int[5]>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
 **is_array\<trivial> == false**  
**is_array\<int> == false**  
**is_array\<int[5]> == true**    
## Requirements  
 **Header:** <type_traits>  
  
 **Namespace:** std  
  
## See Also  
 [<type_traits>](../stdcpplib/-type_traits-.md)   
 [extent Class](../stdcpplib/extent-class.md)   
 [rank Class](../stdcpplib/rank-class.md)
