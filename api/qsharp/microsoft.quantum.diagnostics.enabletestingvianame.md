---
uid: Microsoft.Quantum.Diagnostics.EnableTestingViaName
title: EnableTestingViaName 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EnableTestingViaName
qsharp.summary: Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.
ms.openlocfilehash: 52ec8e670744586f85ee642b0e991734ff91afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201965"
---
# <a name="enabletestingvianame-user-defined-type"></a><span data-ttu-id="a380b-102">EnableTestingViaName 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="a380b-102">EnableTestingViaName user defined type</span></span>

<span data-ttu-id="a380b-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a380b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a380b-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a380b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a380b-105">编译器可识别的属性，通过该属性可以定义可在加载类型时使用的可选名称，也可以将其用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="a380b-105">Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype EnableTestingViaName = (String);
```

