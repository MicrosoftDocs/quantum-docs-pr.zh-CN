---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695866"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="7a5a0-102">HTermsToGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="7a5a0-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="7a5a0-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7a5a0-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="7a5a0-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a5a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a5a0-105">将数据格式的 Hamiltonian 术语的索引转换 `HTerm[]` 为 GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="7a5a0-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="7a5a0-106">输入</span><span class="sxs-lookup"><span data-stu-id="7a5a0-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="7a5a0-107">数据： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="7a5a0-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="7a5a0-108">输入格式的数据 `HTerm[]` 。</span><span class="sxs-lookup"><span data-stu-id="7a5a0-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="7a5a0-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7a5a0-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7a5a0-110">添加到 GeneratorIndex 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7a5a0-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="7a5a0-111">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a5a0-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a5a0-112">Hamiltonian 术语的索引</span><span class="sxs-lookup"><span data-stu-id="7a5a0-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="7a5a0-113">输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7a5a0-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7a5a0-114">表示由表示的 Hamiltonian 术语的 GeneratorIndex `data[idx]` ，以及添加的附加信息 `termType` 。</span><span class="sxs-lookup"><span data-stu-id="7a5a0-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>