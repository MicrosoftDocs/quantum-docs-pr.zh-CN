---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: ApplyConditionallyIntrinsicCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 7cdddba45824d5e5037270d8578f2cb16c03be83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696666"
---
# <a name="applyconditionallyintrinsicca-operation"></a>ApplyConditionallyIntrinsicCA 操作

命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

软件包 [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit
```


## <a name="input"></a>输入

### <a name="measurementresults--__invalidresult__"></a>measurementResults： __无效 <Result>__ []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues： __无效 <Result>__ []




### <a name="onequalop--unit--unit-ctl--adj"></a>onEqualOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词




### <a name="onnonequalop--unit--unit-ctl--adj"></a>onNonEqualOp： [单位](xref:microsoft.quantum.lang-ref.unit) => [单位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

