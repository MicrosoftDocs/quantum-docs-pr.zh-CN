---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844666"
---
# <a name="applyseriesofopsa-operation"></a>ApplySeriesOfOpsA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在数组上按顺序应用 ops 及其目标的列表。  (Adjoint) 

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a>输入

### <a name="listofops--t--unit--is-adj"></a>listOfOps： t [] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 []

要应用的 ops 列表，每个操作都采用 "t" 数组。 它们按顺序应用，最小索引优先。
每个都必须有一个 adjoint 函子


### <a name="targets--int"></a>目标： [Int](xref:microsoft.quantum.lang-ref.int)[] []

描述 op 目标的嵌套数组。 每个数组都应包含一个整数列表，其中包含描述要使用的索引的整数。


### <a name="register--t"></a>注册： t []

要对其进行操作的 Qubit 寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="example"></a>示例

以下应用了 Exp ( [PauliX，PauliY]，0.5) 到 qubits 0，1//then X 到 qubit 2 let ops = [Exp ( [PauliX，PauliY]，0.5，_) ，ApplyToFirstQubitA (X，_) ];let 索引 = [[0，1]，[2]];ApplySeriesOfOpsA (ops，索引，qubitArray) ;

## <a name="see-also"></a>另请参阅

- [Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)