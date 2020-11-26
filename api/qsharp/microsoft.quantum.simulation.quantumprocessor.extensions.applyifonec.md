---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: ApplyIfOneC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: d7c4e39ba26befeabad612e888da4abd00efaeb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230950"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="b1195-102">ApplyIfOneC 操作</span><span class="sxs-lookup"><span data-stu-id="b1195-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="b1195-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b1195-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b1195-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b1195-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="b1195-105">输入</span><span class="sxs-lookup"><span data-stu-id="b1195-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="b1195-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b1195-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-ctl"></a><span data-ttu-id="b1195-107">onResultOneOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="b1195-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="b1195-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="b1195-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="b1195-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1195-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b1195-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="b1195-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1195-111">找</span><span class="sxs-lookup"><span data-stu-id="b1195-111">'T</span></span>

