---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: ApplyIfZero 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: 867e2e78ea787c2376fb2b1dcc6c72694fe08621
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230899"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="11a1d-102">ApplyIfZero 操作</span><span class="sxs-lookup"><span data-stu-id="11a1d-102">ApplyIfZero operation</span></span>

<span data-ttu-id="11a1d-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="11a1d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="11a1d-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="11a1d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="11a1d-105">输入</span><span class="sxs-lookup"><span data-stu-id="11a1d-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="11a1d-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="11a1d-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="11a1d-107">onResultZeroOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11a1d-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="11a1d-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="11a1d-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="11a1d-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11a1d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="11a1d-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="11a1d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="11a1d-111">找</span><span class="sxs-lookup"><span data-stu-id="11a1d-111">'T</span></span>

