---
title: '将其全部放在一起-Q # 技术 |Microsoft Docs'
description: '将其全部放在一起-Q # 技术'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820158"
---
# <a name="putting-it-all-together-teleportation"></a>全部放在一起： Teleportation #
让我们返回到在[量程线路](xref:microsoft.quantum.concepts.circuits)中定义的 teleportation 线路的示例。 我们将使用它来说明我们目前了解到的概念。 下面为不熟悉理论的用户提供了对量程 teleportation 的说明，后面是 Q # 中代码实现的演练。 

## <a name="quantum-teleportation-theory"></a>量程 Teleportation：理论
量程 teleportation 是一种方法，用于将未知的量程状态（我们将称为 "__消息__"）从一个位置中的 qubit 发送到另一个位置中的 qubit （我们将分别指代为 "__此处__" 和 "__存在__" 的 qubits）。 我们可以使用 Dirac 表示法将__消息__表示为矢量： 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

__消息__qubit 的状态未知，因为我们不知道 $ \alpha $ 和 $ \beta $ 的值。

### <a name="step-1-create-an-entangled-state"></a>步骤1：创建放大状态
若要将 qubit 的__消息__发送到__此处__，需要在此处__放大 qubit。__ 为此，可应用 Hadamard 入口，后跟 CNOT-CONTAINS 入口。 让我们看看这些入口操作背后的数学。

我们将从__此处__ __开始，qubits__ $ \ket{0}$ 状态。 Entangling 这些 qubits 后，它们处于以下状态：

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} （\ket{00} + \ket{11}） $ $

### <a name="step-2-send-the-message"></a>步骤2：发送消息
若要发送该__消息__，我们首先将 cnot-contains 入口应用于__消息__qubit 和__此处__qubit 作为输入（此实例中的__消息__qubit 为控件，__此处__qubit 是目标 qubit。） 可以写入此输入状态：

$ $ \ket{\psi}\ket{\phi ^ +} = （\alpha\ket{0} + \beta\ket{1}）（\frac{1}{\sqrt{2}} （\ket{00} + \ket{11}）） $ $

这会扩展到：

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

作为提醒，当 control qubit 为1时，CNOT-CONTAINS 入口将翻转目标 qubit。 例如，$ \ket{000}$ 的输入将导致第一个 qubit （控件）为0时不会发生任何更改。 但是，在第一个 qubit 为1的情况下，例如，$ \ket{100}$ 的输入。 在此实例中，输出为 $ \ket{110}$，因为第二个 qubit （目标）由 CNOT-CONTAINS 入口翻转。

现在，让我们在 CNOT-CONTAINS 入口对以上输入进行操作后，立即考虑输出。 结果为：

$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

发送该__消息__的下一步是将 Hadamard 入口应用到__消息__qubit （这是每个术语的第一 qubit）。 

作为提醒，Hadamard 入口会执行以下操作：

输入 | 输出
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} （\ket{0} + \ket{1}） $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} （\ket{0}-\ket{1}） $

如果我们将 Hadamard 入口应用于上述输出每个术语的第一个 qubit，则会得到以下结果：

$ $ \frac{\alpha}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0} + \ket{1}）） \ket{00} + \frac{\alpha}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0} + \ket{1}）） \ket{11} + \frac{\beta}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0}-\ket{1}）） \ket{10} + \frac{\beta}{\sqrt{2}} （\frac{1}{2}{0}）） \sqrt{1}$ $

请注意，每个术语都有 $2 \frac{1}{\sqrt{2}} $ 系数。 我们可以将这些结果相乘，结果如下：

$ $ \frac{\alpha}{2}（\ket{0} + \ket{1}） \ket{00} + \frac{\alpha}{2}（\ket{0} + \ket{1}） \ket{11} + \frac{\beta}{2}（\ket{0}-\ket{1}） \ket{10} + \frac{\beta}{2}（\ket{0}-\ket{1}） \ket{01} $ $

$ \Frac{1}{2}$ 系数对于每个术语都是通用的，因此我们现在可以将其移到方括号以外：

$ $ \frac{1}{2}\big [\alpha （\ket{0} + \ket{1}） \ket{00} + \alpha （\ket{0} + \ket{1}） \ket{11} + \beta （\ket{0}-\ket{1}） \ket{10} \beta] $ $

然后，可以将每个术语的方括号相乘，提供：

$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>步骤3：度量结果

由于__这里__ __有__放大，__这里__的任何度量都将影响其__状态。__ 如果我们度量第一个和第二个 qubit （__message__和__此处__），我们可以通过牵连的此属性了解上__有__什么状态。 

* 如果度量并获得结果00，则 superposition 会折叠，只保留与此结果一致的术语。 这是 $ \alpha\ket{000} + \beta\ket{001}$。 这可以重构为 $ \ket{00}（\alpha\ket{0} + \beta\ket{1}） $。 因此，如果我们将第一个和第二个 qubit 度量值为__00，我们__知道第三个 qubit 处于状态 $ （\alpha\ket{0} + \beta\ket{1}） $。
* 如果度量并获得结果01，则 superposition 会折叠，只保留与此结果一致的条款。 这是 $ \alpha\ket{011} + \beta\ket{010}$。 这可以重构为 $ \ket{01}（\alpha\ket{1} + \beta\ket{0}） $。 因此，如果我们将第一个和第二个 qubit 度量为__01，我们__知道第三个 qubit 处于状态 $ （\alpha\ket{1} + \beta\ket{0}） $。
* 如果度量并获得结果10，则 superposition 会折叠，只保留与此结果一致的条款。 这是 $ \alpha\ket{100}-\beta\ket{101}$。 这可以重构为 $ \ket{10}（\alpha\ket{0}-\beta\ket{1}） $。 因此，如果我们将第一个和第二个 qubit 度量值为__10，我们__知道第三个 qubit 处于状态 $ （\alpha\ket{0}-\beta\ket{1}） $。
* 如果度量并获得结果11，则 superposition 会折叠，只保留与此结果一致的条款。 这是 $ \alpha\ket{111}-\beta\ket{110}$。 这可以重构为 $ \ket{11}（\alpha\ket{1}-\beta\ket{0}） $。 因此，如果我们将第一个和第二个 qubit 测量为 11 __，则我们__知道第三个 qubit 处于状态 $ （\alpha\ket{1}-\beta\ket{0}） $。

### <a name="step-4-interpret-the-result"></a>步骤4：解释结果

作为提醒，我们希望发送的原始__消息__为：

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

我们需要在此状态中__获取 qubit，__ 以便接收状态是预期的状态。 

* 如果我们测量并得到00的__结果，则__第三个 qubit 的状态为 $ （\alpha\ket{0} + \beta\ket{1}） $。 由于这是预期__消息__，不需要进行任何更改。
* 如果度量结果为__01，则__第三个 qubit 处于状态 $ （\alpha\ket{1} + \beta\ket{0}） $。 这不同于预期的__消息__，但是应用 NOT 入口会给我们提供所需状态 $ （\alpha\ket{0} + \beta\ket{1}） $。
* 如果度量结果为__10，则__第三个 qubit 处于状态 $ （\alpha\ket{0}-\beta\ket{1}） $。 这不同于预期的__消息__，但是，应用 Z 门将为我们提供所需状态 $ （\alpha\ket{0} + \beta\ket{1}） $。
* 如果度量结果为__11，则__第三个 qubit 处于状态 $ （\alpha\ket{1}-\beta\ket{0}） $。 这不同于预期的__消息__，但应用 "NOT" 后跟 Z 门会为我们提供所需状态 $ （\alpha\ket{0} + \beta\ket{1}） $。

总而言之，如果度量值为1，并且第一个 qubit 为1，则应用 Z 入口。 如果度量值为1，第二个 qubit 为1，则应用 NOT 入口。

### <a name="summary"></a>摘要
下面显示了一个用于实现 teleportation 的短信量程线路。 从左到右移动可以看到：
- 步骤 1 __：通过应用__Hadamard__入口和 Cnot-contains 入口，Entangling。__
- 步骤2：使用 CNOT-CONTAINS 入口和 Hadamard 入口发送__消息__。
- 步骤3：度量第一个和第二个 qubits、__消息__和__此处__。
- 步骤4：应用 NOT 入口或 Z 门，具体取决于步骤3中的测量结果。

!["传送（msg： Qubit，存在： Qubit）： Unit"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>量程 Teleportation：代码

我们的线路用于量程 teleportation：

!["传送（msg： Qubit，存在： Qubit）： Unit"](~/media/teleportation.svg)

现在，我们可以将该量程线路中的每个步骤都转换为 Q #。

### <a name="step-0-definition"></a>步骤0：定义
执行 teleportation 时，我们必须知道要发送的消息，以及要将__消息__发送到的位置。 出于此原因，我们首先定义一个新的传送操作，该操作将给定两个 qubits 作为参数，`msg` 和 `there`：

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

我们还需要使用 `using` 块来分配 qubit `here`：

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>步骤1：创建放大状态
然后，可以使用 @"microsoft.quantum.intrinsic.h" 和 @"microsoft.quantum.intrinsic.cnot" 操作在 `here` 和 `there` 之间创建放大对：

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>步骤2：发送消息
然后，使用下一个 $ \operatorname{CNOT} $ 和 $H $ 关口来移动消息 qubit：

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>步骤 3 & 4：测量和解释结果
最后，我们使用 @"microsoft.quantum.intrinsic.m" 执行度量，并执行必要的入口操作以获取所需状态，如 `if` 语句所示：

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

这将完成 teleportation 运算符的定义，因此，我们可以释放 `here`、结束正文并结束操作。

```qsharp
    }
}
```
