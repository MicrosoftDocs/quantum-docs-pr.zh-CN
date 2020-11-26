---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229063"
---
# <a name="applyconditionally-operation"></a>ApplyConditionally 操作

命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>输入

### <a name="measurementresults--__invalidresult__"></a>measurementResults：__无效 <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues：__无效 <Result>__[]




### <a name="onequalop--t--unit"></a>onEqualOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) 




### <a name="equalarg--t"></a>equalArg： t




### <a name="onnonequalop--u--unit"></a>onNonEqualOp： ' U => [单元](xref:microsoft.quantum.lang-ref.unit) 




### <a name="nonequalarg--u"></a>nonEqualArg： ' U





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U

