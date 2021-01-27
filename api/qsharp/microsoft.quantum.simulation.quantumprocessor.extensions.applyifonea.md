---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: ApplyIfOneA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: 63ce44300f6e50cb91294b62611275e3e8942655
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855616"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="6ea5e-102">ApplyIfOneA 操作</span><span class="sxs-lookup"><span data-stu-id="6ea5e-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="6ea5e-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="6ea5e-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6ea5e-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6ea5e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6ea5e-105">输入</span><span class="sxs-lookup"><span data-stu-id="6ea5e-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="6ea5e-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="6ea5e-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj"></a><span data-ttu-id="6ea5e-107">onResultOneOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="6ea5e-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="6ea5e-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="6ea5e-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="6ea5e-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ea5e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6ea5e-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="6ea5e-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ea5e-111">找</span><span class="sxs-lookup"><span data-stu-id="6ea5e-111">'T</span></span>

