---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: b6f7e7d6d51e531b0ec9e7e4f2f5772038421933
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695248"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="7d903-102">ApplyConditionallyA 操作</span><span class="sxs-lookup"><span data-stu-id="7d903-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="7d903-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7d903-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7d903-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7d903-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="7d903-105">输入</span><span class="sxs-lookup"><span data-stu-id="7d903-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="7d903-106">measurementResults： __无效 <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="7d903-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="7d903-107">resultsValues： __无效 <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="7d903-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-adj"></a><span data-ttu-id="7d903-108">onEqualOp：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="7d903-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="7d903-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="7d903-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-adj"></a><span data-ttu-id="7d903-110">onNonEqualOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="7d903-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="7d903-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="7d903-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7d903-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d903-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7d903-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="7d903-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d903-114">找</span><span class="sxs-lookup"><span data-stu-id="7d903-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="7d903-115">' U</span><span class="sxs-lookup"><span data-stu-id="7d903-115">'U</span></span>

