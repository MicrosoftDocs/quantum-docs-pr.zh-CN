---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854302"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState 函数

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个操作，该操作准备给定混合状态的 purification。
"Purified mixed state" 是指窗体的状态 | ψ⟩ = Σi √ pi | i ⟩ | garbagei ⟩由系数 {pi} 指定。 此窗体的状态可以减小到混合状态复数≔ pi | i ⟩⟨ i |通过跟踪 "垃圾" 注册 (即，混合状态在计算基础中是对角的) 。

https://arxiv.org/pdf/1805.03662.pdf?page=15有关进一步的讨论，请参阅。

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>说明

使用量程 ROM 技术来表示给定密度矩阵，并将该表示形式作为状态准备操作返回。

具体而言，给定 $N $ 系数 $ \ alpha_j $ 的列表，此函数返回一个操作，该操作使用量程 ROM 技术来准备近似值 $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ 混合状态 $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |}{\ sum_k | \ alpha_k |}\ket{j}\bra{j}，\end{align} $ $，其中每个 $p _j $ 是给定系数 $ \ alpha_j $ 的近似值，如 $ $ \begin{align} \left |p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}每个 $j $ 的 \frac{\epsilon}{N} \end{align} $ $。

传递索引注册和垃圾 qubits 注册时，最初，在状态 $ \ket {0} \ket{00\cdots 0} 中，返回的操作准备注册到 $ \tilde \rho $，$ $ \begin{align} \ sum_ {j = 0} ^ {N} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}，\end{align} $ $ 这样的 purification，以便在目标错误 $ 制定 $ 中重置并解除分配垃圾寄存器 \epsilon 所需的准备工作。

## <a name="input"></a>输入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目标错误 $ \epsilon $。


### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

$N $ 系数的数组，用于指定基础状态的概率。
负数 $-\ alpha_j $ 将被视为正 $ | \ alpha_j | $。



## <a name="output--mixedstatepreparation"></a>输出： [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

一种操作，用于将 $ \tilde \rho $ 作为 purification 准备到联合索引和垃圾寄存器。

## <a name="example"></a>示例

下面的代码段准备了 $ 3 $-qubit state $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} 的 purification{\ sum_k | \ alpha_k |}\ket{j}\bra{j} $，其中 $ \vec\alpha = (1.0，2.0，3.0，4.0，5.0) $，目标错误为 $10 ^ {-3} $：

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a>备注

为此操作提供的系数按照1个标准进行规范化，以便始终考虑系数来描述有效的分类概率分布。

## <a name="references"></a>参考

- 通过线性线路编码的电子 Spectra，Ryan Babbush、Craig Gidney、Dominic Berry、Nathan Wiebe、Jarrod McClean、Alexandru 暗、奥斯汀 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>另请参阅

- [PurifiedMixedStateWithData。](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)