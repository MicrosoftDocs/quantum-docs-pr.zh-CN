---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856996"
---
# <a name="multim-operation"></a><span data-ttu-id="89b41-102">MultiM 操作</span><span class="sxs-lookup"><span data-stu-id="89b41-102">MultiM operation</span></span>

<span data-ttu-id="89b41-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="89b41-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="89b41-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89b41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89b41-105">按标准度量给定数组中的每个 qubit。</span><span class="sxs-lookup"><span data-stu-id="89b41-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="89b41-106">输入</span><span class="sxs-lookup"><span data-stu-id="89b41-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="89b41-107">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="89b41-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="89b41-108">要测量的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="89b41-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="89b41-109">输出：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="89b41-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="89b41-110">度量结果的数组。</span><span class="sxs-lookup"><span data-stu-id="89b41-110">An array of measurement results.</span></span>