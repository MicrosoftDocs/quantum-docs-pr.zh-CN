---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: f8f4f3b05d3986d94e6f1be380d6c83151d87f17
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230661"
---
# <a name="applyifone-operation"></a><span data-ttu-id="a5901-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="a5901-102">ApplyIfOne operation</span></span>

<span data-ttu-id="a5901-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a5901-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a5901-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a5901-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="a5901-105">输入</span><span class="sxs-lookup"><span data-stu-id="a5901-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="a5901-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a5901-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="a5901-107">onResultOneOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5901-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="a5901-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="a5901-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="a5901-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5901-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a5901-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="a5901-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5901-111">找</span><span class="sxs-lookup"><span data-stu-id="a5901-111">'T</span></span>

