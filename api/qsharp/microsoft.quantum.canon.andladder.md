---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845223"
---
# <a name="andladder-operation"></a>AndLadder 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在目标 qubits 的寄存器上执行受控的 "AND 阶梯"。

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>说明

此操作应用以下映射中描述的转换： $ $ \begin{align} \ket{x \_ 1，\dots ..，x \_ n} \ket{y \_ 1，\dots ..，y \_ {n-1}} \mapsto \ket{x \_ 1，\dots ..，x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2) \dots ..，y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}，\end{align} $ $，其中 $ \ket{x \_ 1，\dots ..，x \_ n} $ 表示的计算基础状态 `controls` ，其中 $ \ket{y \_ 1，\dots ..，y \_ {n-1}} $ 表示计算基础状态 `targets` 。

## <a name="input"></a>输入

### <a name="ccnot--ccnotop"></a>ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

用于构造的 CCNOT 入口。


### <a name="controls--qubit"></a>控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要用作和阶梯控件的 qubits 寄存器。
此操作使计算基础状态保持不 `controls` 变。
的长度 `controls` 必须至少为2，并且必须等于的长度加 1 `targets` 。


### <a name="targets--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

的长度 `targets` 必须至少为1，并且必须等于减1的长度 `controls` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

- 用作和的一部分 <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> 。
- 有关说明和线路关系图，请参阅图4.10： Nielsen & 语中的第4.3 节。

## <a name="references"></a>参考

- [*Michael Nielsen、Isaac 语*、量程计算和量程信息](http://doi.org/10.1017/CBO9780511976667)