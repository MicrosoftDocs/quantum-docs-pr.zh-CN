---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: 2f72da8b470e340d8b283a27643797d41b44592e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855631"
---
# <a name="applyifelserca-operation"></a>ApplyIfElseRCA 操作

命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="measurementresult--__invalidresult__"></a>measurementResult：__无效 <Result>__




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a>onResultZeroOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl




### <a name="zeroarg--t"></a>zeroArg： t




### <a name="onresultoneop--u--unit--is-adj--ctl"></a>onResultOneOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl




### <a name="onearg--u"></a>oneArg： ' U





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U

