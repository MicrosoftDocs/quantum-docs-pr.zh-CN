---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841683"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用单个受控操作的多重控制版本。
修饰符 `CA` 指示 qubit 操作可控制和 adjointable。

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="singlycontrolledop--qubit--unit--is-adj"></a>singlyControlledOp： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

对单个 qubit 控制的操作。
操作的参数中的第一个 qubit 假定为控件，而其余的则假定为目标 qubits。
`ApplyMultiControlled` 始终 `singlyControlledOp` 使用长度至少为1的参数调用。


### <a name="ccnot--ccnotop"></a>ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

用于构造的受控控制的非入口。


### <a name="controls--qubit"></a>控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要对其进行控制的 qubits `singlyControlledOp` 。
的长度 `controls` 必须至少为1。


### <a name="targets--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

作用于的目标 qubits `singlyControlledOp` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

此操作仅使用 clean ancilla qubits。

有关说明和线路关系图，请参阅图4.10，& Nielsen 中的第4.3 节语

## <a name="references"></a>参考

- [*Michael Nielsen、Isaac 语*、量程计算和量程信息](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>另请参阅

- [Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)