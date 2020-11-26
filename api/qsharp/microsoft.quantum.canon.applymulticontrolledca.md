---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209275"
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