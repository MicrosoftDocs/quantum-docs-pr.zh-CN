---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857398"
---
# <a name="applypermutationusingdecomposition-operation"></a>ApplyPermutationUsingDecomposition 操作

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用基于分解的合成，Permutes amplitudes 在量程状态中。

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

此过程实现基于分解的合成方法。  输入是一种排列 $ \pi $ over $ 2 ^ n $ 元素 $ \{ 0，\dots ..，2 ^ n-1 \} $，表示 $n $-可变可逆布尔函数。
算法会对每个可变索引 $i $ 执行以下步骤：

1. 计算 $ ( # A1 \ pi_l，\ pi_r) ，\pi ' ) $，以便 $ \ pi_l $ 和 $ \ pi_r $ 的图像在其元素中的索引（而不是 $ \pi ' $ 的索引）上更改其元素中的位。
2. 设置 $ \pi \leftarrow \pi ' $，并基于不是固定点的元素 pi_r $ pi_l 中派生事实数据表。

将这些步骤应用于所有变量索引后，剩余的排列 $ \pi $ 将是标识，基于收集的事实数据表和索引，可以使用操作来应用事实数据表控制的 @"microsoft.quantum.intrinsic.x" 操作 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" 。

变量顺序为 $0、\dots ..、n-$1。  可以在操作中指定自定义变量顺序 @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" 。

## <a name="input"></a>输入

### <a name="perm--int"></a>永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]

从0开始的 $ 2 ^ n $ 元素的排列。


### <a name="qubits--littleendian"></a>qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

将排列应用到的 $n $ qubits 的列表。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>示例

要合成 `SWAP` 操作：

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>参考

- [*Alexis De Vos*， *Yvan Van Rentergem*，高级. 2 (2) ，2008，pp 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*、 *刘娜 Tague*、 *Gerhard Dueck*、 *Rolf Drechsler*、) 符号计算 73 (2016、pp 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>另请参阅

- [ApplyPermutationUsingDecompositionWithVariableOrder。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [ApplyPermutationUsingTransformation。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)