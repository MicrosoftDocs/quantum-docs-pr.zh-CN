---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: 0a844e0cd8b4faaa28037985918a4d2d187ebc1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700157"
---
# <a name="applyifone-operation"></a><span data-ttu-id="2f421-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="2f421-102">ApplyIfOne operation</span></span>

<span data-ttu-id="2f421-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="2f421-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="2f421-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f421-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="2f421-105">输入</span><span class="sxs-lookup"><span data-stu-id="2f421-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="2f421-106">measurementResult： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="2f421-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="2f421-107">onResultOneOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f421-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="2f421-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="2f421-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="2f421-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f421-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f421-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="2f421-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f421-111">找</span><span class="sxs-lookup"><span data-stu-id="2f421-111">'T</span></span>

