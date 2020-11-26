---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: ApplyConditionallyCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: 18db01f8e5e00c2f115b8ffe73c0f8eea275beb0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230236"
---
# <a name="applyconditionallyca-operation"></a>ApplyConditionallyCA 操作

命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="measurementresults--__invalidresult__"></a>measurementResults：__无效 <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues：__无效 <Result>__[]




### <a name="onequalop--t--unit--is-adj--ctl"></a>onEqualOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl




### <a name="equalarg--t"></a>equalArg： t




### <a name="onnonequalop--u--unit--is-adj--ctl"></a>onNonEqualOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl




### <a name="nonequalarg--u"></a>nonEqualArg： ' U





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U

