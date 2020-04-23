---
title: Q# 技术 - 将其全部放在一起
description: 浏览演示量子传送的基本 Q# 程序。
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030559"
---
# <a name="putting-it-all-together-teleportation"></a>将所有功能放在一起：传送 #
让我们回到[量子电路](xref:microsoft.quantum.concepts.circuits)中定义的传送电路的例子。 我们将用它来说明我们迄今学到的概念。 下面为不熟悉该理论的人提供量子传送的说明，随后在 Q# 中介绍代码实现。 

## <a name="quantum-teleportation-theory"></a>量子传送：理论
量子传送是一种将未知量子状态（我们称之为"__消息__"）从一个位置的量子位发送到另一个位置的量子位的技术（我们将这些量子位分别称为"__此处__"和"__此处__"。 我们可以使用 Dirac 表示法表示我们__的消息__作为矢量： 

$$$\ket_psi] = \alpha\ket{0} ={1} \beta\ket $$$

__消息__qubit 的状态是未知的，因为我们不知道 $_alpha$ 和 $_beta$的值。

### <a name="step-1-create-an-entangled-state"></a>第 1 步：创建纠缠状态
为了__发送消息，我们需要____在这里__的量子位与那里的量子位纠缠在一__起__。 这是通过应用哈达马德门来实现的，然后是 CNOT 门。 让我们来看看这些门操作背后的数学。

我们将从__此处__和__此处__的 qubit 开始，两者都位于{0}$ket $ 状态。 纠缠这些量子位后，它们处于以下状态：

{1}$$$\ket_phi_= = _frac [sqrt]（\ket{2}{00} ={11}\ket） $$$

### <a name="step-2-send-the-message"></a>第 2 步：发送消息
为了__发送消息，我们__首先应用一个带有__消息__qubit的 CNOT 门，__此处__将 qubit 作为输入（__消息__qubit 是控件，__此处__的 qubit 是目标 qubit，在这种情况下）。 可以写入此输入状态：

$$$\ket\psi_ket_ket_phi_]= （\alpha_ket{0} {1}= \beta_ket）（\frac{1}[sqrt]（\ket{2}{00} {11}= \ket）$$

这将扩展到：

$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$

作为提醒，当控件 qubit 为 1 时，CNOT 门将翻转目标量子位。 因此，例如，$_ket{000}$ 的输入不会导致任何变化，因为第一个 qubit（控件）为 0。 但是，以第一个 qubit 为 1 的情况为例 ， 例如{100}，输入为 $_ket $。 在这种情况下，输出为 $_ket{110}$，因为第二个 qubit（目标）由 CNOT 门翻转。

现在，让我们考虑我们的输出，一旦CNOT门已经按照我们上面的意见采取行动。 结果为：

$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$

发送__消息__的下一步是将 Hadamard 门应用于__消息__qubit（这是每个术语的第一个 qubit）。 

作为提醒，哈达马德门执行以下操作：

输入 | 输出
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $_frac{1}\sqrt{2}[（\ket{0} ={1}\ket ）$
$\ket{1}$  | $_frac{1}\sqrt{2}\（\ket{0} -{1}\ket ）$

如果我们将 Hadamard 门应用于上述输出的每个术语的第一个 qubit，我们会得到以下结果：

$${2}_frac_alpha_sqrt _（\frac{1}_sqrt{2}\c \c{0} =ket{1}）\ket{00} \c =\c_\c_\c_\c_\c_sqrt{2}[（\frac{1}_sqrt{2}\c{0} {1}_ket）\ket{11} ]{2}[frac_beta]_sqrt{1}_（\frac{1}_sqrt{10} {2}\c _c_ket{0} ）\ket{2}=\c_beta_sqrt_（_frac{1}_sqrt{2}_（\ket{0} - \ket））\ket{1}{01} $$$$$$$

请注意，每个术语都有两个 $frac{1}\sqrt{2}\$$因子。 我们可以将这些乘数乘以给出以下结果：

$$ [frac_alpha]{2}（\ket{0} ={1}\ket{00} ）\ket{2}={0} \ket{1}\ket ）\ket{11} =\c_beta]（\ket{2}{0} {1}- \ket）\ket{10} {2}=\c_beta]（\ket{0} - \ket）\ket）\ket{1}{01}

$_frac{1}{2}$ 因子是每个术语的通用，因此我们现在可以在括号外将其采用：

$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$

然后，我们可以将每个术语的括号相乘：

$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$

### <a name="step-3-measure-the-result"></a>第 3 步：测量结果

由于__这里____和那里__纠缠，__任何测量在这里__将影响__那里__的状态。 如果我们测量第一个和第二量子位（__消息__和__这里__），我们可以知道__处于__什么状态，由于这种纠缠的属性。 

* 如果我们测量并获取结果 00，叠加将折叠，仅保留与此结果一致的术语。 那是 $_alpha\ket{000} \beta\ket{001}$。 这可以重构为 $\ket{00}（\alpha\ket{0} \beta_ket{1}）$。 因此，如果我们将第一个和第二个 qubit 测量为 00，我们知道第三个 qubit，__有__，处于状态 $（\alpha\ket\beta\ket）$。{0} {1}
* 如果我们测量并获取结果 01，叠加将折叠，仅保留与此结果一致的术语。 那是 $_alpha\ket{011} \beta\ket{010}$。 这可以重构为 $\ket{01}（\alpha\ket{1} \beta_ket{0}）$。 因此，如果我们测量第一个和第二个量子位为 01，我们知道第三个 qubit，__有__，在状态 $（\alpha\ket\beta\ket）$。{1} {0}
* 如果我们测量并获取结果 10，叠加将折叠，仅保留与此结果一致的术语。 那是 $_alpha\ket{100} -\beta\ket{101}$。 这可以重构为 $\ket{10}（\alpha\ket{0} -_beta_ket{1}）$。 因此，如果我们将第一个和第二个量子位度量为 10，我们知道第三个 qubit，__有__，处于状态 $（\alpha_ket-_beta_ket）$。{0} {1}
* 如果我们测量并获取结果 11，叠加将折叠，仅保留与此结果一致的术语。 那是 $_alpha\ket{111} -\beta\ket{110}$。 这可以重构为 $\ket{11}（\alpha\ket{1} -_beta_ket{0}）$。 因此，如果我们将第一个和第二个量子位度量为 11，我们知道第三个 qubit，__有__，处于状态 $（\alpha_ket-_beta_ket）$。{1} {0}

### <a name="step-4-interpret-the-result"></a>第 4 步：解释结果

作为提醒，我们希望发送的原始__信息__是：

$$$\ket_psi] = \alpha\ket{0} ={1} \beta\ket $$$

我们需要将__那里的__qubit 放入此状态，以便接收的状态是预期状态。 

* 如果我们测量并得到的结果为 00，则第三个 qubit，__有__，处于状态 $（\alpha\ket\beta\ket）$。{0} {1} 由于这是预期__的消息__，因此无需更改。
* 如果我们测量并得到 01 的结果，则第三个 qubit，__有__，处于状态 $（\alpha\ket\beta_ket）$。{1} {0} 这与预期__消息__不同，但是应用 NOT 门会给我们所需的状态 $（\alpha\ket\beta\ket）$。{0} {1}
* 如果我们测量并得到 10 的结果，则第三个 qubit，__有__，在状态 $（\alpha\ket{0} -_beta_ket）$。{1} 这与预期__消息__不同，但是应用 Z 门会给我们所需的状态 $（\alpha\ket\beta\ket）$。{0} {1}
* 如果我们测量并得到 11 的结果，那么第三个 qubit，__有__，是在状态 $（\alpha\ket{1} -_beta_ket）$。{0} 这与预期__消息__不同，但是应用 NOT 门后跟 Z 门会给我们所需的状态 $（\alpha\ket\beta_ket）$。{0} {1}

总之，如果我们测量第一个量子位为 1，则应用 Z 门。 如果我们测量第二个量子位为 1，则应用 NOT 门。

### <a name="summary"></a>总结
下面显示了实现传送的教科书量子电路。 从左到右移动，您可以看到：
- 第1步：通过应用哈达马德门和CNOT门，__在这里____和那里__纠缠。
- 第 2 步 __：使用__CNOT 门和哈达马德门发送消息。
- 步骤 3：测量第一和第二个量子位，__消息__和__这里__。
- 步骤 4：根据步骤 3 中的测量结果应用不门或 Z 门。

!['传送（msg ： Qubit， 有 ： Qubit） ： 单位'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>量子传送：代码

我们有用于量子传送的电路：

!['传送（msg ： Qubit， 有 ： Qubit） ： 单位'](~/media/teleportation.svg)

现在，我们可以将此量子电路中的每个步骤转换为 Q#。

### <a name="step-0-definition"></a>步骤 0：定义
当我们执行传送时，我们必须知道我们想要__发送的信息__，以及我们希望发送的位置（__那里__）。 因此，我们首先定义一个新的传送运运运，该操作给定两个 qubit 作为参数`msg`，`there`和 ：

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

我们还需要分配一个通过`here``using`块实现的量子位：

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>第 1 步：创建纠缠状态
然后`here`，我们可以使用`there`@"microsoft.quantum.intrinsic.h"和@"microsoft.quantum.intrinsic.cnot"操作创建 和 之间的纠缠对：

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>第 2 步：发送消息
然后，我们使用下一个 $_运算符名称[CNOT_$ 和 $H$ 门来移动我们的消息库比特：

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>第3步&4：测量和解释结果
最后，我们使用@"microsoft.quantum.intrinsic.m"执行测量并执行必要的门操作以获得所需的状态，如`if`语句所述：

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>第 5 步：重新启动量子位寄存器

在每个 Q# 操作结束时，我们需要让状态中的 qubit $\ket{0}$$。 我们可以使用@"microsoft.quantum.intrinsic.reset"重新启动所有量子位到零状态，这将完成我们的操作。

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


