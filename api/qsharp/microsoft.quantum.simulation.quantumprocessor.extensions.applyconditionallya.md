---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 18ea79e363c28d4fa7aacb69d53a43f6ce39df36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847878"
---
# <a name="applyconditionallya-operation"></a>ApplyConditionallyA 操作

命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a>输入

### <a name="measurementresults--__invalidresult__"></a>measurementResults：__无效 <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues：__无效 <Result>__[]




### <a name="onequalop--t--unit--is-adj"></a>onEqualOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词




### <a name="equalarg--t"></a>equalArg： t




### <a name="onnonequalop--u--unit--is-adj"></a>onNonEqualOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词




### <a name="nonequalarg--u"></a>nonEqualArg： ' U





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U

