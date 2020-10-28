---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: ApplyIfZero 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: a76c6269ac4445326ac357fe2cdd552847089a6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700341"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="6cb97-102">ApplyIfZero 操作</span><span class="sxs-lookup"><span data-stu-id="6cb97-102">ApplyIfZero operation</span></span>

<span data-ttu-id="6cb97-103">命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="6cb97-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6cb97-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6cb97-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="6cb97-105">输入</span><span class="sxs-lookup"><span data-stu-id="6cb97-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="6cb97-106">measurementResult： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="6cb97-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="6cb97-107">onResultZeroOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cb97-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="6cb97-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="6cb97-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="6cb97-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cb97-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6cb97-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="6cb97-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6cb97-111">找</span><span class="sxs-lookup"><span data-stu-id="6cb97-111">'T</span></span>

