---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: ApplyConditionallyIntrinsicC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 847865c04bdaa51cec97826eddcdb95c66001e67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228961"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="12ce7-102">ApplyConditionallyIntrinsicC 操作</span><span class="sxs-lookup"><span data-stu-id="12ce7-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="12ce7-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="12ce7-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="12ce7-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="12ce7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="12ce7-105">输入</span><span class="sxs-lookup"><span data-stu-id="12ce7-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="12ce7-106">measurementResults：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="12ce7-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="12ce7-107">resultsValues：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="12ce7-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-ctl"></a><span data-ttu-id="12ce7-108">onEqualOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="12ce7-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onnonequalop--unit--unit--is-ctl"></a><span data-ttu-id="12ce7-109">onNonEqualOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="12ce7-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="12ce7-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="12ce7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

