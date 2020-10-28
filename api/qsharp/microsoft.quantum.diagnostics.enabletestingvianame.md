---
uid: Microsoft.Quantum.Diagnostics.EnableTestingViaName
title: EnableTestingViaName 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EnableTestingViaName
qsharp.summary: Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.
ms.openlocfilehash: ee4f32a5af4243ad85994c2edd006737a5131931
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695579"
---
# <a name="enabletestingvianame-user-defined-type"></a><span data-ttu-id="1901c-102">EnableTestingViaName 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="1901c-102">EnableTestingViaName user defined type</span></span>

<span data-ttu-id="1901c-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1901c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1901c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1901c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1901c-105">编译器可识别的属性，通过该属性可以定义可在加载类型时使用的可选名称，也可以将其用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="1901c-105">Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype EnableTestingViaName = (String);
```

