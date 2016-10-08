---
title: "Common Problems When Creating a Release Build"
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
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
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
# Common Problems When Creating a Release Build
During development, you will usually build and test with a debug build of your project. If you then build your application for a release build, you may get an access violation.  
  
 The list below shows the primary differences between a debug and a release (nondebug) build. There are other differences, but following are the primary differences that would cause an application to fail in a release build when it works in a debug build.  
  
-   [Heap Layout](#_core_heap_layout)  
  
-   [Compilation](#_core_compilation)  
  
-   [Pointer Support](#_core_pointer_support)  
  
-   [Optimizations](#_core_optimizations)  
  
 See the [/GZ (Catch Release-Build Errors in Debug Build)](../VS_visualcpp/-GZ--Enable-Stack-Frame-Run-Time-Error-Checking-.md) compiler option for information on how to catch release build errors in debug builds.  
  
##  <a name="_core_heap_layout"></a> Heap Layout  
 Heap layout will be the cause of about ninety percent of the apparent problems when an application works in debug, but not release.  
  
 When you build your project for debug, you are using the debug memory allocator. This means that all memory allocations have guard bytes placed around them. These guard bytes detect a memory overwrite. Because heap layout is different between release and debug versions, a memory overwrite might not create any problems in a debug build, but may have catastrophic effects in a release build.  
  
 For more information, see [Check for Memory Overwrite](../VS_visualcpp/Checking-for-Memory-Overwrites.md) and [Use the Debug Build To Check for Memory Overwrite](../VS_visualcpp/Using-the-Debug-Build-to-Check-for-Memory-Overwrite.md).  
  
##  <a name="_core_compilation"></a> Compilation  
 Many of the MFC macros and much of the MFC implementation changes when you build for release. In particular, the ASSERT macro evaluates to nothing in a release build, so none of the code found in ASSERTs will be executed. For more information, see [Examine ASSERT Statements](../VS_visualcpp/Using-VERIFY-Instead-of-ASSERT.md).  
  
 Some functions are inlined for increased speed in the release build. Optimizations are generally turned on in a release build. A different memory allocator is also being used.  
  
##  <a name="_core_pointer_support"></a> Pointer Support  
 The lack of debugging information removes the padding from your application. In a release build, stray pointers have a greater chance of pointing to uninitialized memory instead of pointing to debug information.  
  
##  <a name="_core_optimizations"></a> Optimizations  
 Depending on the nature of certain segments of code, the optimizing compiler might generate unexpected code. This is the least likely cause of release build problems, but it does arise on occasion. For a solution, see [Optimizing Your Code](../VS_visualcpp/Optimizing-Your-Code.md).  
  
## See Also  
 [Release Builds](../VS_visualcpp/Release-Builds.md)   
 [Fixing Release Build Problems](../VS_visualcpp/Fixing-Release-Build-Problems.md)