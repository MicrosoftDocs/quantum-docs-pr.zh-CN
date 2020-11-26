---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsic
title: ApplyIfElseIntrinsic 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsic
qsharp.summary: ''
ms.openlocfilehash: f334c824a48ddc2e0596332b9d58aab2fca982c7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228927"
---
# <a name="applyifelseintrinsic-operation"></a><span data-ttu-id="8c7c5-102">ApplyIfElseIntrinsic 操作</span><span class="sxs-lookup"><span data-stu-id="8c7c5-102">ApplyIfElseIntrinsic operation</span></span>

<span data-ttu-id="8c7c5-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="8c7c5-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="8c7c5-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8c7c5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsic (measurementResult : Result, onResultZeroOp : (Unit => Unit), onResultOneOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="8c7c5-105">输入</span><span class="sxs-lookup"><span data-stu-id="8c7c5-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="8c7c5-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="8c7c5-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit"></a><span data-ttu-id="8c7c5-107">onResultZeroOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c7c5-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onresultoneop--unit--unit"></a><span data-ttu-id="8c7c5-108">onResultOneOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c7c5-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="8c7c5-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c7c5-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

