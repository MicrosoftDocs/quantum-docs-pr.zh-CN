---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: d4306e594c49c0863c1284fc4775b5f3c7d73bda
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855673"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="3025c-102">ApplyIfElseR 操作</span><span class="sxs-lookup"><span data-stu-id="3025c-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="3025c-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="3025c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="3025c-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3025c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="3025c-105">输入</span><span class="sxs-lookup"><span data-stu-id="3025c-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="3025c-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3025c-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="3025c-107">onResultZeroOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3025c-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="3025c-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="3025c-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="3025c-109">onResultOneOp： ' U => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3025c-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="3025c-110">oneArg： ' U</span><span class="sxs-lookup"><span data-stu-id="3025c-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="3025c-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3025c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3025c-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="3025c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3025c-113">找</span><span class="sxs-lookup"><span data-stu-id="3025c-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="3025c-114">' U</span><span class="sxs-lookup"><span data-stu-id="3025c-114">'U</span></span>

