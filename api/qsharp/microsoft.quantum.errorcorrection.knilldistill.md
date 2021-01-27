---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853105"
---
# <a name="knilldistill-operation"></a>KnillDistill 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


实现 Knill 幻状态升华算法。

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>说明

给定15个近似状态 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align} 的 {8} 副本 {1} ，$ $ 会生成一个较高质量的副本。

## <a name="input"></a>输入

### <a name="roughmagic--qubit"></a>roughMagic： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

包含神奇状态近似副本的十五个 qubits 寄存器。 此升华过程的以下应用程序 `roughMagic[0]` 将包含一个较高质量的副本，并且寄存器的其余部分将重置为 $ \ket{00\cdots 0} $ 状态。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

如果为 `true` ，则过程成功并且应接受更高质量的副本。 如果 `false` 为，则过程失败，并且应将寄存器的状态视为未定义。

## <a name="remarks"></a>备注

我们采用 Knill 的算法。
但当前的实现远不是最佳的，因为它使用过多的 qubits。
此例程中注入幻状态，在这种情况下，有更好的协议。

## <a name="references"></a>参考

- [Knill](https://arxiv.org/abs/quant-ph/0402171)