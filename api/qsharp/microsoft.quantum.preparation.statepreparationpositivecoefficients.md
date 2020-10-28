---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700401"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients 函数

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

软件包 [](https://nuget.org/packages/)


返回一个准备给定量程状态的操作。

返回的操作 $U $ 准备任意量程状态 $ \ket{\psi} $，其中正负系数为 $ \ alpha_j \ge $0，$n $-qubit 计算基础状态 $ \ket{0...0} $。

新分配的寄存器上的 U 操作是由 $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}。
\end{align} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

最多 $ 2 ^ n $ 系数 $ \ alpha_j $ 的数组。 $J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。



## <a name="output--littleendian--unit-adj--ctl"></a>输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl

状态准备单一操作 $U $。

## <a name="remarks"></a>注解

负输入系数 $ \ alpha_j < $0 将被视为具有值 $ | \ alpha_j | $ 的正值。 `coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ alpha_j = $0.0 填充。