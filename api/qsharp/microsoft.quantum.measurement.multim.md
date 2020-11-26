---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226989"
---
# <a name="multim-operation"></a><span data-ttu-id="b9149-102">MultiM 操作</span><span class="sxs-lookup"><span data-stu-id="b9149-102">MultiM operation</span></span>

<span data-ttu-id="b9149-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="b9149-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="b9149-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9149-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9149-105">按标准度量给定数组中的每个 qubit。</span><span class="sxs-lookup"><span data-stu-id="b9149-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="b9149-106">输入</span><span class="sxs-lookup"><span data-stu-id="b9149-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="b9149-107">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b9149-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b9149-108">要测量的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="b9149-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="b9149-109">输出：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="b9149-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="b9149-110">度量结果的数组。</span><span class="sxs-lookup"><span data-stu-id="b9149-110">An array of measurement results.</span></span>