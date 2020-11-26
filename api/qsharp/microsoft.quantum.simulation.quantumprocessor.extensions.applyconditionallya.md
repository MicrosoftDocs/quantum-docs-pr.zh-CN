---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 8117fd632b78c24c9ecb8545274eaf296645b645
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230406"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="dc37b-102">ApplyConditionallyA 操作</span><span class="sxs-lookup"><span data-stu-id="dc37b-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="dc37b-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="dc37b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="dc37b-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dc37b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="dc37b-105">输入</span><span class="sxs-lookup"><span data-stu-id="dc37b-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="dc37b-106">measurementResults：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="dc37b-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="dc37b-107">resultsValues：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="dc37b-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="dc37b-108">onEqualOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="dc37b-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="dc37b-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="dc37b-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="dc37b-110">onNonEqualOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="dc37b-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="dc37b-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="dc37b-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="dc37b-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc37b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dc37b-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="dc37b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc37b-114">找</span><span class="sxs-lookup"><span data-stu-id="dc37b-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="dc37b-115">' U</span><span class="sxs-lookup"><span data-stu-id="dc37b-115">'U</span></span>

