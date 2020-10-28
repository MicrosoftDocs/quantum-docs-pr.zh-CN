---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695864"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="32eca-102">HTermsToGenSys 函数</span><span class="sxs-lookup"><span data-stu-id="32eca-102">HTermsToGenSys function</span></span>

<span data-ttu-id="32eca-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="32eca-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="32eca-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32eca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32eca-105">将数据格式的 Hamiltonian 转换 `HTerm[]` 为 GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="32eca-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="32eca-106">输入</span><span class="sxs-lookup"><span data-stu-id="32eca-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="32eca-107">数据： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="32eca-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="32eca-108">输入格式的数据 `HTerm[]` 。</span><span class="sxs-lookup"><span data-stu-id="32eca-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="32eca-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="32eca-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="32eca-110">添加到 GeneratorIndex 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="32eca-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="32eca-111">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="32eca-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="32eca-112">表示由输入表示的 Hamiltonian 的 GeneratorSystem `data` 。</span><span class="sxs-lookup"><span data-stu-id="32eca-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>