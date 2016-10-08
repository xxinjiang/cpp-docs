---
title: "Collection Class Helpers"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 11
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
# Collection Class Helpers
The collection classes             `CMap`,             `CList`, and             `CArray` use templated global helper functions for such purposes as comparing, copying, and serializing elements. As part of your implementation of classes based on             `CMap`,             `CList`, and             `CArray`, you must override these functions as necessary with versions tailored to the type of data stored in your map, list, or array. For information on overriding helper functions such as             `SerializeElements`, see the article             [Collections: How to Make a Type-Safe Collection](../VS_visualcpp/How-to--Make-a-Type-Safe-Collection.md). Note that             **ConstructElements** and             **DestructElements** have been deprecated.  
  
 The Microsoft Foundation Class Library provides the following global functions to help you customize your collection classes:  
  
### Collection Class Helpers  
  
|||  
|-|-|  
|[CompareElements](../Topic/CompareElements.md)|Indicates whether elements are the same.|  
|[CopyElements](../Topic/CopyElements.md)|Copies elements from one array to another.|  
|[DumpElements](../Topic/DumpElements.md)|Provides stream-oriented diagnostic output.|  
|[HashKey](../Topic/HashKey.md)|Calculates a hash key.|  
|[SerializeElements](../Topic/SerializeElements.md)|Stores or retrieves elements to or from an archive.|  
  
##  <a name="compareelements"></a>  CompareElements  
 Called directly by                 [CList::Find](../Topic/CList::Find.md) and indirectly by                 [CMap::Lookup](../Topic/CMap::Lookup.md) and                 [CMap::operator &#91;&#93;](../Topic/CMap::operator.md).  
  
```  
  
template<class  
TYPE  
,  
class  
ARG_TYPE  
>  
BOOL  
AFXAPI  
CompareElements(  
   const  
TYPE  
*  
pElement1  
,  
   const  
ARG_TYPE  
*  
pElement2  
);  
  
```  
  
### Parameters  
 *TYPE*  
 The type of the first element to be compared.  
  
 `pElement1`  
 Pointer to the first element to be compared.  
  
 `ARG_TYPE`  
 The type of the second element to be compared.  
  
 `pElement2`  
 Pointer to the second element to be compared.  
  
### Return Value  
 Nonzero if the object pointed to by                         `pElement1` is equal to the object pointed to by                         `pElement2`; otherwise 0.  
  
### Remarks  
 The                         `CMap` calls use the                         `CMap` template parameters                         *KEY* and                         `ARG_KEY`.  
  
 The default implementation returns the result of the comparison of                         *\*pElement1* and                         *\*pElement2*. Override this function so that it compares the elements in a way that is appropriate for your application.  
  
 The C++ language defines the comparison operator (                        `==`) for simple types (                        `char`,                         `int`,                         **float**, and so on) but does not define a comparison operator for classes and structures. If you want to use                         `CompareElements` or to instantiate one of the collection classes that uses it, you must either define the comparison operator or overload                         `CompareElements` with a version that returns appropriate values.  
  
##  <a name="copyelements"></a>  CopyElements  
 This function is called directly by                 [CArray::Append](../Topic/CArray::Append.md) and                 [CArray::Copy](../Topic/CArray::Copy.md).  
  
```  
  
template<class   
TYPE  
>  
void AFXAPI  
CopyElements(  
TYPE  
*  
pDest  
,  
   const  
TYPE  
*  
pSrc  
,  
   INT_PTR  
nCount  
);  
  
```  
  
### Parameters  
 *TYPE*  
 Template parameter specifying the type of elements to be copied.  
  
 `pDest`  
 Pointer to the destination where the elements will be copied.  
  
 `pSrc`  
 Pointer to the source of the elements to be copied.  
  
 `nCount`  
 Number of elements to be copied.  
  
### Remarks  
 The default implementation uses the simple assignment operator (                         **=** ) to perform the copy operation. If the type being copied does not have an overloaded operator=, then the default implementation performs a bitwise copy.  
  
 For information on implementing this and other helper functions, see the article                         [Collections: How to Make a Type-Safe Collection](../VS_visualcpp/How-to--Make-a-Type-Safe-Collection.md).  
  
##  <a name="dumpelements"></a>  DumpElements  
 Provides stream-oriented diagnostic output in text form for the elements of your collection when overridden.  
  
```  
  
template<class  
TYPE  
>  
void  
AFXAPI  
DumpElements(  
   CDumpContext&  
dc  
,  
   const  
TYPE  
*  
pElements  
,  
   INT_PTR  
nCount  
);  
  
```  
  
### Parameters  
 `dc`  
 Dump context for dumping elements.  
  
 *TYPE*  
 Template parameter specifying the type of the elements.  
  
 `pElements`  
 Pointer to the elements to be dumped.  
  
 `nCount`  
 Number of elements to be dumped.  
  
### Remarks  
 The                         **CArray::Dump**,                         **CList::Dump**, and                         **CMap::Dump** functions call this if the depth of the dump is greater than 0.  
  
 The default implementation does nothing. If the elements of your collection are derived from                         `CObject`, your override will typically iterate through the collection's elements, calling                         `Dump` for each element in turn.  
  
 For information on diagnostics and on the                         `Dump` function, see                         [Debugging MFC Applications](../Topic/MFC%20Debugging%20Techniques.md).  
  
##  <a name="hashkey"></a>  HashKey  
 Calculates a hash value for the given key.  
  
```  
  
template<class  
ARG_KEY  
>  
AFX_INLINE UINT  
AFXAPI  
HashKey(  
ARG_KEY  
key  
);  
  
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the data type used to access map keys.  
  
 `key`  
 The key whose hash value is to be calculated.  
  
### Return Value  
 The key's hash value.  
  
### Remarks  
 This function is called directly by                         [CMap::RemoveKey](../Topic/CMap::RemoveKey.md) and indirectly by                         [CMap::Lookup](../Topic/CMap::Lookup.md) and                         [CMap::Operator &#91;&#93;](../Topic/CMap::operator.md).  
  
 The default implementation creates a hash value by shifting                         `key` right by four positions. Override this function so that it returns hash values appropriate for your application.  
  
### Example  
 [!CODE [NVC_MFC_Utilities#34](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#34)]  
  
##  <a name="serializeelements"></a>  SerializeElements  
 [CArray](../VS_visualcpp/CArray-Class.md),                 [CList](../VS_visualcpp/CList-Class.md), and                 [CMap](../VS_visualcpp/CMap-Class.md) call this function to serialize elements.  
  
```  
  
template<  
class  
TYPE  
>  
void  
AFXAPI  
SerializeElements(  
   CArchive&  
ar  
,  
TYPE  
*  
pElements  
,  
   INT_PTR  
nCount  
);  
  
```  
  
### Parameters  
 *TYPE*  
 Template parameter specifying the type of the elements.  
  
 `ar`  
 An archive object to archive to or from.  
  
 `pElements`  
 Pointer to the elements being archived.  
  
 `nCount`  
 Number of elements being archived  
  
### Remarks  
 The default implementation does a bitwise read or write.  
  
 For information on implementing this and other helper functions, see the article                         [Collections: How to Make a Type-Safe Collection](../VS_visualcpp/How-to--Make-a-Type-Safe-Collection.md).  
  
### Example  
 See the example in the article                                 [Collections: How to Make a Type-Safe Collection](../VS_visualcpp/How-to--Make-a-Type-Safe-Collection.md).  
  
## See Also  
 [Macros and Globals](../VS_visualcpp/MFC-Macros-and-Globals.md)   
 [CMap Class](../VS_visualcpp/CMap-Class.md)   
 [CList Class](../VS_visualcpp/CList-Class.md)   
 [CArray Class](../VS_visualcpp/CArray-Class.md)