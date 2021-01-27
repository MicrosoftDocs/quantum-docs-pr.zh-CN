---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: d4306e594c49c0863c1284fc4775b5f3c7d73bda
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855673"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR 操作

命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a>输入

### <a name="measurementresult--__invalidresult__"></a>measurementResult：__无效 <Result>__




### <a name="onresultzeroop--t--unit"></a>onResultZeroOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) 




### <a name="zeroarg--t"></a>zeroArg： t




### <a name="onresultoneop--u--unit"></a>onResultOneOp： ' U => [单元](xref:microsoft.quantum.lang-ref.unit) 




### <a name="onearg--u"></a>oneArg： ' U





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U

