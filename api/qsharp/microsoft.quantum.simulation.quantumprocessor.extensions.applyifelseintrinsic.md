---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsic
title: ApplyIfElseIntrinsic 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsic
qsharp.summary: ''
ms.openlocfilehash: 0bb2446e123996a8f3e70ed20868203ebebd0510
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696665"
---
# <a name="applyifelseintrinsic-operation"></a><span data-ttu-id="1c8c6-102">ApplyIfElseIntrinsic 操作</span><span class="sxs-lookup"><span data-stu-id="1c8c6-102">ApplyIfElseIntrinsic operation</span></span>

<span data-ttu-id="1c8c6-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="1c8c6-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="1c8c6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c8c6-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseIntrinsic (measurementResult : Result, onResultZeroOp : (Unit => Unit), onResultOneOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="1c8c6-105">输入</span><span class="sxs-lookup"><span data-stu-id="1c8c6-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="1c8c6-106">measurementResult： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="1c8c6-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit"></a><span data-ttu-id="1c8c6-107">onResultZeroOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c8c6-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onresultoneop--unit--unit"></a><span data-ttu-id="1c8c6-108">onResultOneOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c8c6-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="1c8c6-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c8c6-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

