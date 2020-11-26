---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: 6fbf186575775b3ae18a41727c225fb871f8dac0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192615"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="4f0f4-102">ApplyIfElseRCA 操作</span><span class="sxs-lookup"><span data-stu-id="4f0f4-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="4f0f4-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="4f0f4-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="4f0f4-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4f0f4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4f0f4-105">输入</span><span class="sxs-lookup"><span data-stu-id="4f0f4-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="4f0f4-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="4f0f4-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="4f0f4-107">onResultZeroOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="4f0f4-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="4f0f4-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="4f0f4-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-adj--ctl"></a><span data-ttu-id="4f0f4-109">onResultOneOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="4f0f4-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="4f0f4-110">oneArg： ' U</span><span class="sxs-lookup"><span data-stu-id="4f0f4-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="4f0f4-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f0f4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4f0f4-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="4f0f4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4f0f4-113">找</span><span class="sxs-lookup"><span data-stu-id="4f0f4-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="4f0f4-114">' U</span><span class="sxs-lookup"><span data-stu-id="4f0f4-114">'U</span></span>

