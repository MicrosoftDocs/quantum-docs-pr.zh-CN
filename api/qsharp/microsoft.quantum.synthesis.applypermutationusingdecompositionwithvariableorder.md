---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701088"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>ApplyPermutationUsingDecompositionWithVariableOrder 操作

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


使用基于分解的合成，Permutes amplitudes 在量程状态中。

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

此操作是 @"microsoft.quantum.synthesis.applypermutationusingdecomposition" 可在其中指定可变顺序的更通用版本。 不同的变量顺序将更改分解序列和用于受控入口的事实数据表 @"microsoft.quantum.intrinsic.x" 。  因此，更改可变顺序会改变用于实现排列的总入口数。

## <a name="input"></a>输入

### <a name="perm--int"></a>永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]

从0开始的 $ 2 ^ n $ 元素的排列。


### <a name="variableorder--int"></a>variableOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]

从0开始 $n $ 元素的排列。


### <a name="qubits--littleendian"></a>qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

将排列应用到的 $n $ qubits 的列表。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [ApplyPermutationUsingDecomposition。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [ApplyPermutationUsingTransformation。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)