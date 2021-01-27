---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: e82df36d2e4f3767a152d5c92d7b1897c744a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840684"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回为给定操作实现 Trotter – Suzuki 集成器的操作。

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="nsteps--int"></a>nSteps： [Int](xref:microsoft.quantum.lang-ref.int)

要分解为时间步长的操作数。


### <a name="op--intdoublet--unit--is-adj--ctl"></a>op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，is =) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

接受 (类型的索引输入 `Int`) 和时间输入 (类型 `Double` 为分解的) 的操作。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

选择要使用的 Trotter – Suzuki 集成器的顺序。
订单1，甚至订单2，4，6,.。。当前支持。



## <a name="output--doublet--unit--is-adj--ctl"></a>输出： ([Double](xref:microsoft.quantum.lang-ref.double)，t) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

返回一个实现 Trotter – Suzuki 集成器的单一参数，其中第一个参数 `Double` 是集成步骤大小，第二个参数是目标。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每次步骤应执行的操作的类型;通常为 `Qubit[]` 或 `Qubit` 。

## <a name="remarks"></a>备注

当使用 `order` 等于时 `1` ，此函数将返回一个操作，该操作可由最低顺序 Trotter – Suzuki 集成器 $ $ \begin{align} S_1 ( \lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}，\end{align} $ $，我们已遵循 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139) 的表示法，并让 $ \lambda $ 成为) 的第一次输入所表示的演化时间 (并让 $ \{ H_j \} _ {j = 1} ^ {m} $ 是要集成的 (Hermitian) dynamical 生成器的集合，这 `op(j, lambda, _)` 是由单一运算符 $e ^ {H_j \lambda} $ 模拟的。

同样， `order` `2` 返回第二顺序对称 Trotter – Suzuki 集成器 $ $ \begin{align} S_2 ( \lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}。
\end{align} $ $

更高的值 `order` 是使用 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139)的递归构造实现的。

## <a name="references"></a>参考

- [*D. Berry，Ahokas，Cleve，Sanders，，*](https://arxiv.org/abs/quant-ph/0508139)