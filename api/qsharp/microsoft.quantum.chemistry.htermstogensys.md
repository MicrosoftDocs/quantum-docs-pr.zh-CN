---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204107"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="6831b-102">HTermsToGenSys 函数</span><span class="sxs-lookup"><span data-stu-id="6831b-102">HTermsToGenSys function</span></span>

<span data-ttu-id="6831b-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6831b-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="6831b-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6831b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6831b-105">将数据格式的 Hamiltonian 转换 `HTerm[]` 为 GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="6831b-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="6831b-106">输入</span><span class="sxs-lookup"><span data-stu-id="6831b-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="6831b-107">数据： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="6831b-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="6831b-108">输入格式的数据 `HTerm[]` 。</span><span class="sxs-lookup"><span data-stu-id="6831b-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="6831b-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6831b-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6831b-110">添加到 GeneratorIndex 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="6831b-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="6831b-111">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="6831b-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="6831b-112">表示由输入表示的 Hamiltonian 的 GeneratorSystem `data` 。</span><span class="sxs-lookup"><span data-stu-id="6831b-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>