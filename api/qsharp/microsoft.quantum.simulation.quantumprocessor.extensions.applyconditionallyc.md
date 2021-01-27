---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: ApplyConditionallyC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 09496d384a70fa9fb6826304ce9909034297a118
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847854"
---
# <a name="applyconditionallyc-operation"></a>ApplyConditionallyC 操作

命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a>输入

### <a name="measurementresults--__invalidresult__"></a>measurementResults：__无效 <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues：__无效 <Result>__[]




### <a name="onequalop--t--unit--is-ctl"></a>onEqualOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl




### <a name="equalarg--t"></a>equalArg： t




### <a name="onnonequalop--u--unit--is-ctl"></a>onNonEqualOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl




### <a name="nonequalarg--u"></a>nonEqualArg： ' U





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U

