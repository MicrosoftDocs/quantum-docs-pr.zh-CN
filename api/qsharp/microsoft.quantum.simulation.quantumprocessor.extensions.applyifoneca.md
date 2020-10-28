---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: ApplyIfOneCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: d8f388698c0c6d1557c7903ec68b317728986031
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701201"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="261e0-102">ApplyIfOneCA 操作</span><span class="sxs-lookup"><span data-stu-id="261e0-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="261e0-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="261e0-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="261e0-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="261e0-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="261e0-105">输入</span><span class="sxs-lookup"><span data-stu-id="261e0-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="261e0-106">measurementResult： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="261e0-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-ctl--adj"></a><span data-ttu-id="261e0-107">onResultOneOp：不等于> [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词</span><span class="sxs-lookup"><span data-stu-id="261e0-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="261e0-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="261e0-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="261e0-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="261e0-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="261e0-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="261e0-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="261e0-111">找</span><span class="sxs-lookup"><span data-stu-id="261e0-111">'T</span></span>

