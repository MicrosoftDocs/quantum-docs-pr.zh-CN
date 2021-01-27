---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 6e956038f7cd15db7348ff830da8bc9eae53aa61
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855561"
---
# <a name="applyxcontrolledontruthtable-operation"></a>ApplyXControlledOnTruthTable 操作

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


@"microsoft.quantum.intrinsic.x" `target` 如果布尔函数的 `func` 计算结果为 true （对于中的传统分配），则应用操作 `controlRegister` 。

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

此操作实现单一操作 \begin{align} U\ket {x} \ 票证 {y} = \ket{x}\ket{y \oplus f (x) } \end{align}，其中 $x $ 和 $y $ `controlRegister` 分别表示和 `target` 。

$F $ 的布尔函数以大整数表示为事实数据表。
例如，在三个输入中的多数函数由 bitstring 表示 `11101000` ，其中最高有效位 `1` 对应于输入分配 `(1, 1, 1)` ，并且最小有效位对应于 `0` 输入分配 `(0, 0, 0)` 。
它可以用十六进制表示法中的大整数表示， `0xE8L` 或以 `232L` 十进制表示法表示。  `L`后缀指示常数的类型为 `BigInt` 。
有关此表示形式的更多详细信息，请参阅 [kata 表](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)。

实现利用 @"microsoft.quantum.intrinsic.cnot" 和 @"microsoft.quantum.intrinsic.r1" 入口。

## <a name="input"></a>输入

### <a name="func--bigint"></a>func： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

表示为大整数的布尔事实数据表


### <a name="controlregister--qubit"></a>controlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册控制 qubits


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

目标 qubit



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

- [*Schuch*， *Siewert*，PRL 91，no，027902，2003，arXiv： quant-ph/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken*， *圣马丁 Roetteler*，arXiv：2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>另请参阅

- [ApplyXControlledOnTruthTableWithCleanTarget。](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)