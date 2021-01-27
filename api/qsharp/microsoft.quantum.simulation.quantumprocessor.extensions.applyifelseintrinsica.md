---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicA
title: ApplyIfElseIntrinsicA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: f8a2c494bcda6687f3f51044cf4c923213e9d218
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855720"
---
# <a name="applyifelseintrinsica-operation"></a><span data-ttu-id="85f77-102">ApplyIfElseIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="85f77-102">ApplyIfElseIntrinsicA operation</span></span>

<span data-ttu-id="85f77-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="85f77-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="85f77-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="85f77-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsicA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Adj), onResultOneOp : (Unit => Unit is Adj)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="85f77-105">输入</span><span class="sxs-lookup"><span data-stu-id="85f77-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="85f77-106">measurementResult：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="85f77-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit--is-adj"></a><span data-ttu-id="85f77-107">onResultZeroOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="85f77-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onresultoneop--unit--unit--is-adj"></a><span data-ttu-id="85f77-108">onResultOneOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="85f77-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="85f77-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85f77-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

