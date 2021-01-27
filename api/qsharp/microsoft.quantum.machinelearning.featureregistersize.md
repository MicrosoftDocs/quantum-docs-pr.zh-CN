---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848428"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="ac528-102">FeatureRegisterSize 函数</span><span class="sxs-lookup"><span data-stu-id="ac528-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="ac528-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ac528-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ac528-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ac528-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ac528-105">返回对特定功能向量进行编码所需的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="ac528-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="ac528-106">输入</span><span class="sxs-lookup"><span data-stu-id="ac528-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="ac528-107">示例： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ac528-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ac528-108">要编码到 qubit 寄存器中的示例功能向量。</span><span class="sxs-lookup"><span data-stu-id="ac528-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="ac528-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac528-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac528-110">编码为 qubit 寄存器所需的大小 `sample` ，以 qubits 数表示。</span><span class="sxs-lookup"><span data-stu-id="ac528-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>