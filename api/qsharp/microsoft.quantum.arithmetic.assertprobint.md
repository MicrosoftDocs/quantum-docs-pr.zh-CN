---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843410"
---
# <a name="assertprobint-operation"></a>AssertProbInt 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言量程寄存器的特定状态的概率具有预期值。

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>说明

如果给定 $n $-qubit 量程状态 $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $，则断言 $ $j 索引的状态 $ \ket{j} $ 的概率 $ | \ alpha_j | ^ 2 $ 具有预期值。

## <a name="input"></a>输入

### <a name="stateindex--int"></a>stateIndex： [Int](xref:microsoft.quantum.lang-ref.int)

由寄存器表示的状态 $ \ket{j} $ 的索引 $j $ `LittleEndian` 。


### <a name="expected--double"></a>应为： [Double](xref:microsoft.quantum.lang-ref.double)

$ | \ Alpha_j | ^ 2 $ 的预期值。


### <a name="qubits--littleendian"></a>qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以小字节序格式存储 $ \ket{\psi} $ 的 qubit 寄存器。


### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

实际值与预期值的绝对容差。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>示例

假设注册将 `qubits` qubit 的量程状态 $ \ket{\psi} = \ sqrt {1/8} \ 票证 {0} + \ sqrt {7/8} \ 票证 $ 编码为 {6} 小 endian 格式。
这意味着数字状态 $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ 和 $ \ket \equiv\ket \ket {6} {0} {1} \ket {1} $。 以下断言成功：

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```