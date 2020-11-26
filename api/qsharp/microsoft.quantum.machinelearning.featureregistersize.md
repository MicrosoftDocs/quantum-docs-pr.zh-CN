---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196406"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="7a542-102">FeatureRegisterSize 函数</span><span class="sxs-lookup"><span data-stu-id="7a542-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="7a542-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7a542-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7a542-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7a542-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7a542-105">返回对特定功能向量进行编码所需的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="7a542-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="7a542-106">输入</span><span class="sxs-lookup"><span data-stu-id="7a542-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="7a542-107">示例： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7a542-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7a542-108">要编码到 qubit 寄存器中的示例功能向量。</span><span class="sxs-lookup"><span data-stu-id="7a542-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="7a542-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a542-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a542-110">编码为 qubit 寄存器所需的大小 `sample` ，以 qubits 数表示。</span><span class="sxs-lookup"><span data-stu-id="7a542-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>