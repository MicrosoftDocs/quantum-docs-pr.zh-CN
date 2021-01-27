---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 67a4dcba5c193222c06ab429813adf12d7bbedfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847884"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="1c836-102">ApplyConditionally 操作</span><span class="sxs-lookup"><span data-stu-id="1c836-102">ApplyConditionally operation</span></span>

<span data-ttu-id="1c836-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="1c836-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="1c836-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1c836-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="1c836-105">输入</span><span class="sxs-lookup"><span data-stu-id="1c836-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="1c836-106">measurementResults：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="1c836-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="1c836-107">resultsValues：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="1c836-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="1c836-108">onEqualOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c836-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="1c836-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="1c836-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="1c836-110">onNonEqualOp： ' U => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c836-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="1c836-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="1c836-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="1c836-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c836-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1c836-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="1c836-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1c836-114">找</span><span class="sxs-lookup"><span data-stu-id="1c836-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="1c836-115">' U</span><span class="sxs-lookup"><span data-stu-id="1c836-115">'U</span></span>

