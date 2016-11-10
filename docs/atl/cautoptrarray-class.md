---
title: "CAutoPtrArray Class"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoPtrArray<E>"
  - "CAutoPtrArray"
  - "ATL::CAutoPtrArray"
  - "ATL.CAutoPtrArray<E>"
  - "ATL.CAutoPtrArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtrArray class"
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: 16
ms.author: "mblome"
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
# CAutoPtrArray Class
This class provides methods useful when constructing an array of smart pointers.  
  
> [!IMPORTANT]
>  This class and its members cannot be used in applications that execute in the Windows Runtime.  
  
## Syntax  
  
```
template<
    typename   E>
    class  CAutoPtrArray : public CAtlArray<
    ATL::CAutoPtr<E>,
    CAutoPtrElementTraits<E>>
```  
  
#### Parameters  
 `E`  
 The pointer type.  
  
## Members  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](../Topic/CAutoPtrArray::CAutoPtrArray.md)|The constructor.|  
  
## Remarks  
 This class provides a constructor and derives methods from [CAtlArray](../atl/catlarray-class.md) and [CAutoPtrElementTraits](../atl/cautoptrelementtraits-class.md) to aid the creation of a collection class object storing smart pointers.  
  
 For more information, see [ATL Collection Classes](../atl/atl-collection-classes.md).  
  
## Inheritance Hierarchy  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## Requirements  
 **Header:** atlcoll.h  
  
##  <a name="cautoptrarray__cautoptrarray"></a>  CAutoPtrArray::CAutoPtrArray  
 The constructor.  
  
```
CAutoPtrArray() throw();
```  
  
### Remarks  
 Initializes the smart pointer array.  
  
## See Also  
 [CAtlArray Class](../atl/catlarray-class.md)   
 [CAutoPtrElementTraits Class](../atl/cautoptrelementtraits-class.md)   
 [CAutoPtrList Class](../atl/cautoptrlist-class.md)   
 [Class Overview](../atl/atl-class-overview.md)
