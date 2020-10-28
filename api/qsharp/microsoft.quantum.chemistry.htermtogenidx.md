---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695863"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="eee80-102">HTermToGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="eee80-102">HTermToGenIdx function</span></span>

<span data-ttu-id="eee80-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="eee80-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="eee80-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eee80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eee80-105">将数据格式的 Hamiltonian 术语转换 `HTerm` 为 GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="eee80-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="eee80-106">输入</span><span class="sxs-lookup"><span data-stu-id="eee80-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="eee80-107">术语： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="eee80-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="eee80-108">输入格式的数据 `HTerm` 。</span><span class="sxs-lookup"><span data-stu-id="eee80-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="eee80-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="eee80-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="eee80-110">添加到 GeneratorIndex 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="eee80-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="eee80-111">输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="eee80-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="eee80-112">表示由表示的 Hamiltonian 术语的 GeneratorIndex `term` ，以及添加的附加信息 `termType` 。</span><span class="sxs-lookup"><span data-stu-id="eee80-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>