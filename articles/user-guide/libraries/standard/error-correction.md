---
title: 'Q # 标准库中的纠错'
description: '了解如何在你的 Q # 程序中使用纠错代码，同时保护 qubits 的状态。'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 514fe68f603b9a3a0b4607390719b08a43fe4967
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274413"
---
# <a name="error-correction"></a>错误更正 #

## <a name="introduction"></a>简介 ##

在传统计算中，如果有一位要防范错误，通常可以通过重复数据位来用*逻辑位*来表示该位。
例如，让 $ \overline {0} = $0 是数据位0的编码，其中使用标签0上面的一行来指示它是0状态中位的编码。
如果我们以类似的方式让 $ \overline {1} = $111，则我们有一个简单的重复代码，可以防止出现一位翻转错误。
也就是说，如果三个位中有任何一个进行了翻转，则可以通过使用大多数投票来恢复逻辑位的状态。
尽管传统的纠错是此特定示例中的一个更加丰富的主题（我们建议不要再[介绍编码理论](https://www.springer.com/us/book/9783540641339)），但上面的重复代码已经指向了一个可能存在的问题来保护量程信息。
也就是说，"[无克隆" 定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem)意味着如果我们测量每个单独的 qubit，并通过与上面的传统代码进行交叉投票，就会丢失我们尝试保护的准确信息。

在量程设置中，我们会看到测量值有问题。 我们仍可以实现上述编码。
这样做有助于了解我们如何将错误更正通用化到量程情况。
因此，让 $ \ket{\overline {0} } = \ket {000} = \ket {0} \otimes \ket {0} \otimes \ket {0} $，并让 $ \ket{\overline {1} } = \ket {111} $。
然后，按线性，为所有输入定义重复代码;例如，$ \ket{\overline{+}} = （\ket{\overline {0} } + \ket{\overline {1} }）/\sqrt {2} = （\ket {000} + \ket {111} ）/\sqrt {2} $。
具体而言，在 qubit 中使用 _1 $ act $X 时，请注意，这两个分支中所需的更正都精确地 $X _1 $： $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left （X_1 \ket {000} + X_1 \ket {111} \right） \\ \\ & = \frac {1} {\sqrt {2} } \left （\ket {010} + \ket {101} \right）。
\end{align} $ $

若要查看我们如何确定这种情况，而无需测量我们尝试保护的状态，可以记下每个不同的位翻转错误对逻辑状态的操作：

| 错误 $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ |
| $X_0$ | $ \ket {100} $ | $ \ket {011} $ |
| $X_1$ | $ \ket {010} $ | $ \ket {101} $ |
| $X_2$ | $ \ket {001} $ | $ \ket {110} $ |

为了保护我们正在编码的状态，我们需要能够区分三个错误，并将其从标识 $ \boldone $ 区分开来，而不区分 $ \ket{\overline {0} } $ 和 $ \ket{\overline {1} } $。
例如，如果度量值为 $Z _0 $， {0} 则在无错误情况下，为 $ \ket{\overline} $ 和 $ \ket{\overline} $ 获取不同的结果 {1} ，以便折叠已编码状态。
另一方面，请考虑在每个计算基础状态下测量 Z_1 $ $Z _0 的前两位的奇偶校验。
回忆一下，Pauli 运算符的每个度量值都会检查正在测量的状态对应的 eigenvalue，因此对于上表中的每个状态 $ \ket{\psi} $，我们都可以计算 $Z _0 Z_1 \ket{\psi} $，以查看是否获得 $ \pm\ket{\psi} $。
请注意，$Z _0 Z_1 \ket {000} = \ket {000} $ and，$Z _0 Z_1 \ket {111} = \ket {111} $，因此，我们得出这一度量值对这两种编码状态执行相同的操作。
另一方面，$Z _0 Z_1 \ket {100} =-\ket {100} $ and $Z _0 Z_1 \ket {011} =-\ket {011} $，因此衡量 $Z _0 Z_1 $ 的结果将显示有关发生了哪些错误的有用信息。

为了强调这一点，请重复上述表，但在每一行上添加度量 $Z _0 Z_1 $ 和 $Z _1 Z_2 $ 的结果。
我们通过分别与 and 的 Q # 值相对应的 eigenvalue 的符号表示每个度量值的结果： $ + $ 或 $-$ `Result` `Zero` `One` 。

| 错误 $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ | $Z _0 的结果 Z_1 $ | $Z _1 Z_2 $ 的结果 |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ | $+$ | $+$ |
| $X_0$ | $ \ket {100} $ | $ \ket {011} $ | $-$ | $+$ |
| $X_1$ | $ \ket {010} $ | $ \ket {101} $ | $-$ | $-$ |
| $X_2$ | $ \ket {001} $ | $ \ket {110} $ | $+$ | $-$ |

因此，两个度量值的结果可唯一确定发生了哪个位翻转错误，但不会泄漏有关所编码的状态的任何信息。
我们将这些结果称为 "不*症状*"，并参阅将一个症状映射回导致其*恢复*的错误的过程。
特别是，我们强调，恢复是一种*传统*的推理过程，该过程会将发生的症状作为其输入，并返回一个指示，说明如何修复可能发生的任何错误。

> [!NOTE]
> 以上的位翻转代码只能纠正单个位翻转错误;也就是说， `X` 操作在单个 qubit 上。
> 如果应用 `X` 于多个 qubit，将在恢复后将 $ \ket{\overline {0} } $ 映射到 $ \ket{\overline {1} } $。
> 同样，应用阶段翻转操作 `Z` 会将 $ \ket{\overline {1} } $ 映射到 $-\ket{\overline {1} } $，因此会将 $ \ket{\overline{+}} $ 映射到 $ \ket{\overline {-} } $。
> 通常，可以创建代码来处理更多错误，并处理 $Z $ 个错误以及 $X $ 个错误。

对于在所有代码状态下以相同方式操作的量程错误更正，我们可以对其进行描述，这就是*稳定的形式*。
Q # canon 提供了一个框架，用于描述从稳定程序代码进行的编码和解码，并描述了一个从错误中恢复的方法。
在本部分中，我们使用几个简单的量程纠错代码描述此框架及其应用程序。

> [!TIP]
> 稳定介绍了对稳定形式的介绍。
> 我们向读者介绍了了解更多[Gottesman 2009](https://arxiv.org/abs/0904.2557)的兴趣。

## <a name="representing-error-correcting-codes-in-q"></a>表示问答中的纠错代码# ##

为了帮助指定错误更正代码，Q # canon 提供了几个不同的用户定义类型：

- <xref:microsoft.quantum.errorcorrection.logicalregister>`= Qubit[]`：表示 qubits 的寄存器应解释为纠错代码的代码块。
- <xref:microsoft.quantum.errorcorrection.syndrome>`= Result[]`：表示度量结果的数组应解释为在代码块上测量的症状。
- <xref:microsoft.quantum.errorcorrection.recoveryfn>`= (Syndrome -> Pauli[])`：表示*传统*函数应用于解释症状并返回应应用的更正。
- <xref:microsoft.quantum.errorcorrection.encodeop>`= ((Qubit[], Qubit[]) => LogicalRegister)`：表示操作使用表示数据的 qubits 和全新的 ancilla qubits，以生成错误更正代码的代码块。
- <xref:microsoft.quantum.errorcorrection.decodeop>`= (LogicalRegister => (Qubit[], Qubit[]))`：表示一个操作，分解将错误更正代码的代码块转换为数据 qubits，并使用 ancilla qubits 表示症状信息。
- <xref:microsoft.quantum.errorcorrection.syndromemeasop>`= (LogicalRegister => Syndrome)`：表示一个操作，该操作应用于从代码块中提取症状信息，而不会影响由代码保护的状态。

最后，canon 提供 <xref:microsoft.quantum.errorcorrection.qecc> 类型以收集定义量程错误更正代码所需的其他类型。 与每个稳定量程代码相关联的代码长度为： $ $n $、逻辑 qubits 的数字 $k $，$d $，最小距离 $，通常以表示法⟦ $n $，$k $，$d $ ⟧。 例如， <xref:microsoft.quantum.errorcorrection.bitflipcode> 函数定义⟦3，1，1⟧位翻转代码：

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

请注意，该 `QECC` 类型*不*包含恢复功能。
这样，我们就可以更改在更正错误时使用的恢复功能，而无需更改代码本身的定义;此功能在将信息从特征度量纳入到恢复所假定的模型时特别有用。

以这种方式定义代码后，可以使用该 <xref:microsoft.quantum.errorcorrection.recover> 操作从错误中恢复：

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

我们将在[位翻转代码示例](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)中更详细地探讨这一点。

除了位翻转代码外，Q # canon 还提供了[5 qubit 完美代码](https://arxiv.org/abs/quant-ph/9602019)的实现和[七 qubit 代码](https://arxiv.org/abs/quant-ph/9705052)，这两者都可以更正任意单 qubit 错误。
