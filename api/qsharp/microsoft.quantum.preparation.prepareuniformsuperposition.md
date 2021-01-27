---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854316"
---
# <a name="prepareuniformsuperposition-operation"></a>PrepareUniformSuperposition 操作

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


创建对 superposition 进行编码的状态为0的统一 `nIndices - 1` 。

也就是说，在给定输入状态 $ \ket{0\cdots 0} $ 的情况下，此单一 $U $ 将在所有数字状态 $0 $ 到 $M-$1 上创建一个统一的 superposition。 换句话说，$ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}。
\end{align} $ $。

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="nindices--int"></a>nIndices： [Int](xref:microsoft.quantum.lang-ref.int)

统一 superposition 中所需的状态数 $M $。


### <a name="indexregister--littleendian"></a>indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以格式存储数字状态的 qubit 寄存器 `LittleEndian` 。
此注册必须能够将数字存储 $M-$1，并假定在状态 $ \ket{0\cdots 0} $ 中进行初始化。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>示例

下面的示例准备 {1} $3 $ qubits 上的状态 $ \frac {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $。

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a>备注

此操作为 adjointable，但 `indexRegister` `nIndices` 在这种情况下，要求在 superposition 的基础上是统一的。