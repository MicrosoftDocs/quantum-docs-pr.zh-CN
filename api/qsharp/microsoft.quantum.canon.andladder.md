---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696391"
---
# <a name="andladder-operation"></a>AndLadder 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


在目标 qubits 的寄存器上执行受控的 "AND 阶梯"。

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
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



## <a name="remarks"></a>注解

- 用作和的一部分 <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> 。
- 有关说明和线路关系图，请参阅图4.10： Nielsen & 语中的第4.3 节。

## <a name="references"></a>参考

- [*Michael Nielsen、Isaac 语* 、量程计算和量程信息](http://doi.org/10.1017/CBO9780511976667)