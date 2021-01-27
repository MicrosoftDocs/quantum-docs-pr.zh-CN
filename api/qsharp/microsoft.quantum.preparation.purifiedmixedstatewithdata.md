---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854282"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData 函数

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个操作，该操作准备具有给定混合状态的 purification，并使用表示给定数据集合的寄存器放大。
"带有数据的 purified 混合状态" 指的是Σi √ pi | i ⟩ | xi ⟩ | garbagei ⟩格式的状态，其中每个 xi 都是一个 bitstring 编码其他与 register 关联的数据 | i ⟩。

https://arxiv.org/pdf/1805.03662.pdf?page=15有关进一步的讨论，请参阅。

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>说明

使用量程 ROM 技术来表示给定密度矩阵，并将该表示形式作为状态准备操作返回。

具体而言，给定 $N $ 系数 $ \ alpha_j $ 的列表和 _与每个系数关联的 bitstring $ \vec{x} j $，此函数返回一个操作，该操作使用量程 ROM 技术来准备近似值 $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ of 混合状态 $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |}{\ sum_k | \ alpha_k |}\ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}，\end{align} $ $，其中的每个 $p _j $ 是给定系数 $ \ alpha_j $ 的近似值，$ $ \begin{align} \left |p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}每个 $j $ 的 \frac{\epsilon}{N} \end{align} $ $。

传递索引注册和垃圾 qubits 注册时，最初在状态 $ \ket {0} \ket{00\cdots 0} 中，返回的操作准备注册到 $ \tilde \rho $，$ $ \begin{align} \ sum_ {j = 0} ^ {N} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}，\end{align} $ $ 这样的操作，以便在目标错误 $ 制定 $ 中重置和取消分配垃圾寄存器 \epsilon 所需的准备工作。

## <a name="input"></a>输入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目标错误 $ \epsilon $。


### <a name="coefficients--doublebool"></a>系数： ([Double](xref:microsoft.quantum.lang-ref.double)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) []

$N $ 系数的数组，用于指定基础状态的概率，以及与每个系数关联的 bitstring $ \vec{x} _j $。
负数 $-\ alpha_j $ 将被视为正 $ | \ alpha_j | $。



## <a name="output--mixedstatepreparation"></a>输出： [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

一种操作，用于将 $ \tilde \rho $ 作为 purification 准备到联合索引和垃圾寄存器。

## <a name="remarks"></a>备注

为此操作提供的系数按照1个标准进行规范化，以便始终考虑系数来描述有效的分类概率分布。

## <a name="references"></a>参考

- 通过线性线路编码的电子 Spectra，Ryan Babbush、Craig Gidney、Dominic Berry、Nathan Wiebe、Jarrod McClean、Alexandru 暗、奥斯汀 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>另请参阅

- [PurifiedMixedState。](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)