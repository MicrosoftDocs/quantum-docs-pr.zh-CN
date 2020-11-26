---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicA
title: ApplyIfElseIntrinsicA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: 12144630d1ffe0210c5979db0a94dc5267f17d30
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230151"
---
# <a name="applyifelseintrinsica-operation"></a><span data-ttu-id="bd348-102">ApplyIfElseIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="bd348-102">ApplyIfElseIntrinsicA operation</span></span>

<span data-ttu-id="bd348-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="bd348-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="bd348-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bd348-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsicA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Adj), onResultOneOp : (Unit => Unit is Adj)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bd348-105">输入</span><span class="sxs-lookup"><span data-stu-id="bd348-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="bd348-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="bd348-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit--is-adj"></a><span data-ttu-id="bd348-107">onResultZeroOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="bd348-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onresultoneop--unit--unit--is-adj"></a><span data-ttu-id="bd348-108">onResultOneOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="bd348-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="bd348-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd348-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

