---
title: "Provider Wizard-Generated Files | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB providers, wizard-generated files"
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: 7
author: "mikeblome"
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
# Provider Wizard-Generated Files
The ATL OLE DB Provider Wizard generates the following files. The following topics use the short name "MyProvider", but the exact file names depend on the choice you made when creating the provider.  
  
|File name|Description|  
|---------------|-----------------|  
|MyProviderRS.cpp|Contains the command helper `Execute` method and the provider column map.|  
|MyProviderDS.h|Implements the data source object. This header file contains the property map for data source properties.|  
|MyProviderRS.h|Implements the command and rowset objects. This header file contains the property map for rowset and command properties.|  
|MyProviderSess.h|Implements the session object. This header file contains the property map for session properties.|  
|MyProvider.rgs|Contains the registered objects generated by the OLE DB Provider Wizard.|  
  
## See Also  
 [Creating an OLE DB Provider](../../data/oledb/creating-an-ole-db-provider.md)