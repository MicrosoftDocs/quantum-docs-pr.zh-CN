---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: PrepareArbitraryState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18f45da601b02fc5f83936b086323e31a66fc20b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700729"
---
# <a name="preparearbitrarystate-operation"></a>PrepareArbitraryState 操作

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

软件包 [](https://nuget.org/packages/)


给定一组系数和一个小 endian 编码的量程寄存器，就给定的系数所描述的那个寄存器的状态进行准备。

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

此操作将准备一个具有复杂系数的任意量程状态 $ \ket{\psi} $ $r _j e ^ {$n t_j 计算基础状态 $ \ket{0 \cdots 0} $。
具体而言，此操作的操作可以通过单一转换 $U $ 来模拟，该转换作用于全零状态

$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。
\end{align} $ $

## <a name="input"></a>输入

### <a name="coefficients--complexpolar"></a>系数： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

由最多 $ 2 ^ n $ 个复数系数表示的数组，其绝对值和阶段 $ (r_j，t_j) $。 $J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。


### <a name="qubits--littleendian"></a>qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit 寄存器编码号状态（以小字节序格式）。 这应在计算基础状态 $ \ket{0...0} $ 中进行初始化。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

负的输入系数 $r 将被视为值为 $ | r_j | $ 的 _j < $0。 `coefficients` 将用元素 $ (r_j，t_j) = (0.0，0.0) $ （如果指定少于 $ 2 ^ n $）。

## <a name="references"></a>参考

- 量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>另请参阅

- [ApproximatelyPrepareArbitraryState。](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)