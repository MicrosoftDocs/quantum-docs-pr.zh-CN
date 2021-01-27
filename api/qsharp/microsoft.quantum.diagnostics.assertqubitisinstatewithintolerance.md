---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829783"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>AssertQubitIsInStateWithinTolerance 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


断言处于预期状态的 qubit。

`expected` 表示复杂向量，$ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $。
元组的第一个元素表示每个 $a $，$b $ 是复数的实部，第二个元素是复数的实部。
最后一个参数定义进行断言的公差。

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>输入

### <a name="expected--complexcomplex"></a>应为： ([复杂](xref:Microsoft.Quantum.Math.Complex)的[复杂](xref:Microsoft.Quantum.Math.Complex)) 

需要分别为 $ \ket {0} $ 和 $ \ket $ 的复杂 amplitudes {1} 。


### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要断言其状态的 Qubit。 请注意，假定此 qubit 与其他已分配的 qubits 分离，而不是放大。


### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

允许实际 amplitudes 偏离预期值的附加容差。
有关详细信息，请参阅下面的备注。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>示例

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a>备注

以下 Mathematica 代码可用于验证 mi、mx、my、mz 的表达式：

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

容差是 \_ 三维实向量 (x ₂之间的 $L {\infty} $ 距离。 x ₃、x ₄) 由 $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ 和实矢量 (y ₂、y ₃、y ₄定义，) 由复数 = Y ₁ I + y ₂ x + y ₃ y + y ₄ Z 定义，其中复数是与寄存器状态相对应的密度矩阵。
这在假设 Tr (复数) 和 Tr (| ψ⟩⟨ψ |) 都是 1 (例如 x ₁ = 1/2、y ₁ = 1/2) 。
如果不是这种情况，则该函数将断言 (x ₂-x ₁，x ₃-x ₁，x ₄-x ₁，x ₄ + x ₁) 和 (y ₂-y ₁，y ₃ + y ₁) 小于公差参数的∞距离。