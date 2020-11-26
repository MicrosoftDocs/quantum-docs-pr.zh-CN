---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicA
title: ApplyConditionallyIntrinsicA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: d815467b714d1a529e784c2d8519e981cf4750b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230219"
---
# <a name="applyconditionallyintrinsica-operation"></a><span data-ttu-id="f8978-102">ApplyConditionallyIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="f8978-102">ApplyConditionallyIntrinsicA operation</span></span>

<span data-ttu-id="f8978-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="f8978-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f8978-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f8978-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Adj), onNonEqualOp : (Unit => Unit is Adj)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f8978-105">输入</span><span class="sxs-lookup"><span data-stu-id="f8978-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="f8978-106">measurementResults：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="f8978-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="f8978-107">resultsValues：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="f8978-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-adj"></a><span data-ttu-id="f8978-108">onEqualOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="f8978-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onnonequalop--unit--unit--is-adj"></a><span data-ttu-id="f8978-109">onNonEqualOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="f8978-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="f8978-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8978-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

