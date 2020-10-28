---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: 978964888a89ca46847ae7aa01a2c180ee322436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701196"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="8b4a4-102">ApplyIfZeroCA 操作</span><span class="sxs-lookup"><span data-stu-id="8b4a4-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="8b4a4-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="8b4a4-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="8b4a4-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b4a4-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="8b4a4-105">输入</span><span class="sxs-lookup"><span data-stu-id="8b4a4-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="8b4a4-106">measurementResult： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="8b4a4-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl--adj"></a><span data-ttu-id="8b4a4-107">onResultZeroOp：不等于> [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词</span><span class="sxs-lookup"><span data-stu-id="8b4a4-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="8b4a4-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="8b4a4-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="8b4a4-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b4a4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8b4a4-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="8b4a4-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b4a4-111">找</span><span class="sxs-lookup"><span data-stu-id="8b4a4-111">'T</span></span>

