---
uid: Microsoft.Quantum.Synthesis.Extended
title: 扩展函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 9109a05c795f351a4973e1600ce291cdeb94a280
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701057"
---
# <a name="extended-function"></a><span data-ttu-id="946ba-102">扩展函数</span><span class="sxs-lookup"><span data-stu-id="946ba-102">Extended function</span></span>

<span data-ttu-id="946ba-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="946ba-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="946ba-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="946ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="946ba-105">通过反转系数扩展色谱</span><span class="sxs-lookup"><span data-stu-id="946ba-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="946ba-106">输入</span><span class="sxs-lookup"><span data-stu-id="946ba-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="946ba-107">色谱： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="946ba-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="946ba-108">Spectral 系数</span><span class="sxs-lookup"><span data-stu-id="946ba-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="946ba-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="946ba-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="946ba-110">系数，后跟倒副本</span><span class="sxs-lookup"><span data-stu-id="946ba-110">Coefficients followed by inverted copy</span></span>