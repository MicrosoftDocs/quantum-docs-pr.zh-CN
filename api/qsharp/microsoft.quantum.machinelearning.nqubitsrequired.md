---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: 8f6c1bf3dfef3152a6ba8eada0980d6940724259
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854968"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="788c5-102">NQubitsRequired 函数</span><span class="sxs-lookup"><span data-stu-id="788c5-102">NQubitsRequired function</span></span>

<span data-ttu-id="788c5-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="788c5-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="788c5-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="788c5-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="788c5-105">返回应用给定顺序分类器所需的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="788c5-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="788c5-106">输入</span><span class="sxs-lookup"><span data-stu-id="788c5-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="788c5-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="788c5-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="788c5-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="788c5-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="788c5-109">可以应用顺序分类器的寄存器的最小大小。</span><span class="sxs-lookup"><span data-stu-id="788c5-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>