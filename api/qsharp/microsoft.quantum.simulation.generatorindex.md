---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858381"
---
# <a name="generatorindex-user-defined-type"></a>GeneratorIndex 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示所有 dynamical 生成器（如 Hermitian 运算符）集中的单个基元术语，该生成器存在一个从该生成器到该生成器的时间演化的映射 `EvolutionSet` 。

第一个元素 (Int []，Double [] ) 是单个字词的索引，例如，系数为0.5 的 Pauli 字符串 XXY 将按 ( [1，1，2]，[0.5] ) 进行索引。 另外，可以通过 ( []、[φ] ) 以连续变量（例如 X cos φ + Y sin φ）表示的 Hamiltonians。 第二个元素对生成器在其上操作的子系统进行索引。

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>示例

使用  <xref:microsoft.quantum.simulation.paulievolutionset> 时，运算符 $ \pi X_2 X_5 Y_9 $ 表示为：

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>备注

> [!WARNING]
> `GeneratorIndex`除引用一组特定生成器外，未定义的解释。

## <a name="see-also"></a>另请参阅

- [EvolutionSet。](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [PauliEvolutionSet。](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)