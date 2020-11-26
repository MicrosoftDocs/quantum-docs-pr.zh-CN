---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202186"
---
# <a name="assertqubitwithintolerance-operation"></a>AssertQubitWithinTolerance 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


断言 qubit `q` 位于 Pauli Z 运算符的预期 eigenstate 中，直到达到给定的容差。

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>输入

### <a name="expected--__invalidresult__"></a>应为 __： <Result> 无效__

Qubit 应采用的状态： `Zero` 或 `One` 。


### <a name="q--qubit"></a>问： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

其状态为 "已断言" 的 qubit。


### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

对 qubit 测量返回预期结果的概率的公差。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 允许对任意 qubit 的状态进行断言，而不只是 $Z $ eigenstates。

## <a name="see-also"></a>另请参阅

- [AssertQubitIsInStateWithinTolerance。](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)