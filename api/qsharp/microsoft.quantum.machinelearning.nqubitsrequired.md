---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: d7ed687e9c75ed7cc71917aa1cdf32a6fbb93106
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700596"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="6b2ae-102">NQubitsRequired 函数</span><span class="sxs-lookup"><span data-stu-id="6b2ae-102">NQubitsRequired function</span></span>

<span data-ttu-id="6b2ae-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6b2ae-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6b2ae-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b2ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b2ae-105">返回应用给定顺序分类器所需的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="6b2ae-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="6b2ae-106">输入</span><span class="sxs-lookup"><span data-stu-id="6b2ae-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="6b2ae-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="6b2ae-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="6b2ae-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b2ae-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6b2ae-109">可以应用顺序分类器的寄存器的最小大小。</span><span class="sxs-lookup"><span data-stu-id="6b2ae-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>