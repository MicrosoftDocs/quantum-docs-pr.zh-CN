---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: ApplyConditionallyCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: 18db01f8e5e00c2f115b8ffe73c0f8eea275beb0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230236"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="2e8d2-102">ApplyConditionallyCA 操作</span><span class="sxs-lookup"><span data-stu-id="2e8d2-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="2e8d2-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="2e8d2-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="2e8d2-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2e8d2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2e8d2-105">输入</span><span class="sxs-lookup"><span data-stu-id="2e8d2-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="2e8d2-106">measurementResults：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="2e8d2-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="2e8d2-107">resultsValues：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="2e8d2-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj--ctl"></a><span data-ttu-id="2e8d2-108">onEqualOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2e8d2-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="2e8d2-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="2e8d2-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj--ctl"></a><span data-ttu-id="2e8d2-110">onNonEqualOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2e8d2-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="2e8d2-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="2e8d2-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="2e8d2-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e8d2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2e8d2-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="2e8d2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e8d2-114">找</span><span class="sxs-lookup"><span data-stu-id="2e8d2-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="2e8d2-115">' U</span><span class="sxs-lookup"><span data-stu-id="2e8d2-115">'U</span></span>

