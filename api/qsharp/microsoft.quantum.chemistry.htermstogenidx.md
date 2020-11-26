---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216007"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="f2ad4-102">HTermsToGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="f2ad4-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="f2ad4-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f2ad4-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="f2ad4-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f2ad4-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f2ad4-105">将数据格式的 Hamiltonian 术语的索引转换 `HTerm[]` 为 GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="f2ad4-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="f2ad4-106">输入</span><span class="sxs-lookup"><span data-stu-id="f2ad4-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="f2ad4-107">数据： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="f2ad4-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="f2ad4-108">输入格式的数据 `HTerm[]` 。</span><span class="sxs-lookup"><span data-stu-id="f2ad4-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="f2ad4-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f2ad4-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f2ad4-110">添加到 GeneratorIndex 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f2ad4-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="f2ad4-111">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2ad4-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2ad4-112">Hamiltonian 术语的索引</span><span class="sxs-lookup"><span data-stu-id="f2ad4-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="f2ad4-113">输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f2ad4-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f2ad4-114">表示由表示的 Hamiltonian 术语的 GeneratorIndex `data[idx]` ，以及添加的附加信息 `termType` 。</span><span class="sxs-lookup"><span data-stu-id="f2ad4-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>