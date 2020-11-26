---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229063"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="97b79-102">ApplyConditionally 操作</span><span class="sxs-lookup"><span data-stu-id="97b79-102">ApplyConditionally operation</span></span>

<span data-ttu-id="97b79-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="97b79-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="97b79-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="97b79-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="97b79-105">输入</span><span class="sxs-lookup"><span data-stu-id="97b79-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="97b79-106">measurementResults：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="97b79-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="97b79-107">resultsValues：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="97b79-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="97b79-108">onEqualOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97b79-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="97b79-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="97b79-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="97b79-110">onNonEqualOp： ' U => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97b79-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="97b79-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="97b79-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="97b79-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97b79-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="97b79-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="97b79-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="97b79-114">找</span><span class="sxs-lookup"><span data-stu-id="97b79-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="97b79-115">' U</span><span class="sxs-lookup"><span data-stu-id="97b79-115">'U</span></span>

