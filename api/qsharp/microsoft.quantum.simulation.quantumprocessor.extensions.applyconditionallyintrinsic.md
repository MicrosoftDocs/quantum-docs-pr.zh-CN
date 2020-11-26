---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsic
title: ApplyConditionallyIntrinsic 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsic
qsharp.summary: ''
ms.openlocfilehash: 71233ce9c8d07da4748c3bb2197fbb78c8ee617d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228978"
---
# <a name="applyconditionallyintrinsic-operation"></a><span data-ttu-id="49c66-102">ApplyConditionallyIntrinsic 操作</span><span class="sxs-lookup"><span data-stu-id="49c66-102">ApplyConditionallyIntrinsic operation</span></span>

<span data-ttu-id="49c66-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="49c66-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="49c66-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="49c66-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsic (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit), onNonEqualOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="49c66-105">输入</span><span class="sxs-lookup"><span data-stu-id="49c66-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="49c66-106">measurementResults：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="49c66-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="49c66-107">resultsValues：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="49c66-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit"></a><span data-ttu-id="49c66-108">onEqualOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49c66-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onnonequalop--unit--unit"></a><span data-ttu-id="49c66-109">onNonEqualOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49c66-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="49c66-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49c66-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

