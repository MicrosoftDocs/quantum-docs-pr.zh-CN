---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700405"
---
# <a name="statepreparationcomplexcoefficients-function"></a>StatePreparationComplexCoefficients 函数

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

软件包 [](https://nuget.org/packages/)


返回准备特定量程状态的操作。

返回的操作 $U $ 准备带有复数系数的任意量程状态 $ \ket{\psi} $ $r 从 $n $-qubit 计算基础状态 $ \ket{0...0} $ _j e ^ {i t_j} $。

新分配的寄存器上的 U 操作由 $ $ \begin{align} U\ket {0 ... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。
\end{align} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="coefficients--complexpolar"></a>系数： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

由最多 $ 2 ^ n $ 个复数系数表示的数组，其绝对值和阶段 $ (r_j，t_j) $。 $J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。



## <a name="output--littleendian--unit-adj--ctl"></a>输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl

状态准备单一操作 $U $。

## <a name="remarks"></a>注解

负的输入系数 $r 将被视为值为 $ | r_j | $ 的 _j < $0。 `coefficients` 将用元素 $ (r_j，t_j) = (0.0，0.0) $ （如果指定少于 $ 2 ^ n $）。