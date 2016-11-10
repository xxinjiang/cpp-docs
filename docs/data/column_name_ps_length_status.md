---
title: "COLUMN_NAME_PS_LENGTH_STATUS"
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
  - "COLUMN_NAME_PS_LENGTH_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_PS_LENGTH_STATUS macro"
ms.assetid: a1a2e2ca-f0ae-4896-8aa3-67a96c270b05
caps.latest.revision: 7
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
# COLUMN_NAME_PS_LENGTH_STATUS
Represents a binding on the rowset to the specific column in the rowset. Similar to [COLUMN_NAME](../data/column_name.md), except that this macro also takes precision, scale, column length, and column status.  
  
## Syntax  
  
```  
  
COLUMN_NAME_PS_LENGTH_STATUS(  
pszName  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
,   
status )  
```  
  
#### Parameters  
 `pszName`  
 [in] A pointer to the column name. The name must be a Unicode string. You can accomplish this by putting an 'L' in front of the name, for example: `L"MyColumn"`.  
  
 `nPrecision`  
 [in] The maximum precision of the column you want to bind.  
  
 `nScale`  
 [in] The scale of the column you want to bind.  
  
 `data`  
 [in] The corresponding data member in the user record.  
  
 *length*  
 [in] The variable to be bound to the column length.  
  
 *status*  
 [in] The variable to be bound to the column status.  
  
## Remarks  
 See [COLUMN_NAME](../data/column_name.md) for information on where the **COLUMN_NAME_\*** macros are used.  
  
## Requirements  
 **Header:** atldbcli.h  
  
## See Also  
 [Macros and Global Functions for OLE DB Consumer Templates](../data/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../data/begin_accessor.md)   
 [BEGIN_ACCESSOR_MAP](../data/begin_accessor_map.md)   
 [BEGIN_COLUMN_MAP](../data/begin_column_map.md)   
 [COLUMN_NAME](../data/column_name.md)   
 [COLUMN_NAME_EX](../data/column_name_ex.md)   
 [COLUMN_NAME_LENGTH](../data/column_name_length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../data/column_name_length_status.md)   
 [COLUMN_NAME_STATUS](../data/column_name_status.md)   
 [COLUMN_NAME_PS](../data/column_name_ps.md)   
 [COLUMN_NAME_PS_LENGTH](../data/column_name_ps_length.md)   
 [COLUMN_NAME_PS_STATUS](../data/column_name_ps_status.md)   
 [COLUMN_NAME_TYPE](../data/column_name_type.md)   
 [COLUMN_NAME_TYPE_PS](../data/column_name_type_ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../data/column_name_type_size.md)   
 [COLUMN_NAME_TYPE_STATUS](../data/column_name_type_status.md)