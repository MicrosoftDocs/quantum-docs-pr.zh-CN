---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: ApplyIfElseRA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: bcc52c6e2b4dfc6354e12c57e19739ac021d2e8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701121"
---
# <a name="applyifelsera-operation"></a>ApplyIfElseRA 操作

命名空间： [QuantumProcessor。](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

软件包 [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit
```


## <a name="input"></a>输入

### <a name="measurementresult--__invalidresult__"></a>measurementResult： __无效 <Result>__




### <a name="onresultzeroop--t--unit-adj"></a>onResultZeroOp：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 形容词




### <a name="zeroarg--t"></a>zeroArg： t




### <a name="onresultoneop--u--unit-adj"></a>onResultOneOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词




### <a name="onearg--u"></a>oneArg： ' U





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U

