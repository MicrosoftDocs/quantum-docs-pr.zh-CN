---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: ApplyConditionallyC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 09496d384a70fa9fb6826304ce9909034297a118
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847854"
---
# <a name="applyconditionallyc-operation"></a><span data-ttu-id="caba0-102">ApplyConditionallyC 操作</span><span class="sxs-lookup"><span data-stu-id="caba0-102">ApplyConditionallyC operation</span></span>

<span data-ttu-id="caba0-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="caba0-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="caba0-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="caba0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="caba0-105">输入</span><span class="sxs-lookup"><span data-stu-id="caba0-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="caba0-106">measurementResults：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="caba0-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="caba0-107">resultsValues：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="caba0-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-ctl"></a><span data-ttu-id="caba0-108">onEqualOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="caba0-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="caba0-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="caba0-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-ctl"></a><span data-ttu-id="caba0-110">onNonEqualOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="caba0-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="caba0-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="caba0-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="caba0-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="caba0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="caba0-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="caba0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="caba0-114">找</span><span class="sxs-lookup"><span data-stu-id="caba0-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="caba0-115">' U</span><span class="sxs-lookup"><span data-stu-id="caba0-115">'U</span></span>

