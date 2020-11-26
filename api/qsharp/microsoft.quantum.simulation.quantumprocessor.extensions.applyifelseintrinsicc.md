---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicC
title: ApplyIfElseIntrinsicC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 9cd58f2fd103237213ef386fc6af1451e48b7cec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228876"
---
# <a name="applyifelseintrinsicc-operation"></a><span data-ttu-id="2ef22-102">ApplyIfElseIntrinsicC 操作</span><span class="sxs-lookup"><span data-stu-id="2ef22-102">ApplyIfElseIntrinsicC operation</span></span>

<span data-ttu-id="2ef22-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="2ef22-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="2ef22-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2ef22-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsicC (measurementResult : Result, onResultZeroOp : (Unit => Unit is Ctl), onResultOneOp : (Unit => Unit is Ctl)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="2ef22-105">输入</span><span class="sxs-lookup"><span data-stu-id="2ef22-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="2ef22-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="2ef22-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit--is-ctl"></a><span data-ttu-id="2ef22-107">onResultZeroOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="2ef22-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onresultoneop--unit--unit--is-ctl"></a><span data-ttu-id="2ef22-108">onResultOneOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="2ef22-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="2ef22-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ef22-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

