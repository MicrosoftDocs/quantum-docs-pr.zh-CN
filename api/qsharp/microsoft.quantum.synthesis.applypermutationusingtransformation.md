---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: b7196c592690a00da49b17f52b30536ba97b6035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701085"
---
# <a name="applypermutationusingtransformation-operation"></a>ApplyPermutationUsingTransformation 操作

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


使用基于转换的合成，将 amplitudes Permutes 为量程状态。

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

此过程实现基于单向转换的合成方法。  输入是一种排列 $ \pi $ over $ 2 ^ n $ 元素 $ \{ 0，\dots ..，2 ^ n-1 \} $，表示 $n $-可变可逆布尔函数。
算法以迭代方式执行以下步骤：

1. 查找 $x \ne \pi (x) = y $ 的最小 $x $。
2. 查找多个受控制的 Toffoli 操作，这些操作应用于输出使 $ \pi (x) = x $，而不会更改所有 $x < x $ 的 $ \pi (x ' ) $

## <a name="input"></a>输入

### <a name="perm--int"></a>永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]

从0开始的 $ 2 ^ n $ 元素的排列。


### <a name="qubits--littleendian"></a>qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

将排列应用到的 $n $ qubits 的列表。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

- [*D. Michael 莎莎* ， *Dmitri Maslov* ， *Gerhard DUECK* ，Proc 2003，IEEE，pp 318-323，2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken* ， *Gerhard Dueck* ， *d. Michael 莎莎* ，Proc 2016，springer link，pp 307-321，2016](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>另请参阅

- [ApplyPermutationUsingDecomposition。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)