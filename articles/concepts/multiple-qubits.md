---
title: 多个量子位
description: 了解如何在两个或多个 qubits 上执行操作。
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 2fa227c823cd87df9c799c043c699e4ce818b8e3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907539"
---
# <a name="multiple-qubits"></a>多个 Qubits

尽管 qubit 入口具有一些计数器直观的功能（例如，在给定时间内处于多个状态的功能），但如果在一段时间内所有的量程计算机中都有 qubit 入口，那么我们会有一个设备，其计算能力会受到微不足道即使是计算器，也只是传统 cray。
仅当我们增加 qubits 的数量时，量程计算的真正功能才会变得明显。
此功能在某种程度上导致，因为量程状态向量的矢量空间的尺寸随 qubits 的数量呈指数增长。
这意味着，虽然可以对单个 qubit 进行完全建模，但模拟 50 qubit 的量程计算会导致推送现有超级计算机的限制。
增加计算的大小只需一个额外的 qubit 就会使存储状态所需的内存*翻倍*，并大致使计算时间*加倍*。
这种快速计算能力翻倍的原因是，具有相对较小 qubits 数的量程计算机可能远远超过今天、明天和其他计算任务的最强大超级计算机。

为什么要为量程状态向量增加指数级增长？  本部分的目的是查看用于从单 qubit 状态中构建多 qubit 状态的规则，并讨论我们需要包括在设置为构成通用多 qubit 量程计算机的入口中的操作。
这些工具绝对是了解 Q # 代码中常见使用的入口集的必要，还可以获得直觉，例如牵连或干扰的量程效果如何比传统计算功能更强大。

## <a name="representing-two-qubits"></a>表示两个 Qubits
Qubit 状态之间的主要区别在于两 qubit 状态为四维，而不是二维。
这是因为，qubit 状态的计算基础由一 qubit 状态的 tensor 产品构成。  例如，我们有 \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}，\qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\\\\\ 0 \end{bmatrix}，\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}，\qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}。
\end{align}

更常见的情况是，使用此构造，可以很容易看到 $n $ qubits 的量程状态由维度 $ 2 ^ n $ 的单位向量表示。  矢量

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ alpha_{10} \\\\ alpha_ \{11} \end{bmatrix} $ $

表示两个 qubits 上的量程状态： $ | \ alpha_{00}| ^ 2 + | \ alpha_{01}| ^ 2 + | \ alpha_{10}| ^ 2 + | \ alpha_{11}| ^ 2 = 1 $。 与单个 qubits 一样，多个 qubits 的量程状态向量包含描述系统行为所需的所有信息。

如果提供两个单独的 qubits，其中一个处于状态 $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $，另一个 qubit 处于状态 $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $，则对应的双 qubit 状态为

$ $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \\\\ \beta\delta \end{bmatrix}, $$

其中，操作 $ \otimes $ 称为矢量的 tensor 产品（或 Kronecker 产品）。 请注意，尽管我们始终可以采用两个 qubit 状态的 tensor 产品来形成两 qubit 状态，但并不是所有的 qubit 量程状态都可以作为两个单 tensor 状态的 qubit 产品来编写。
例如，没有状态 $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ 和 $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $，以确保其 tensor 产品是状态 

$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

这种 qubit 状态（不能编写为单 qubit 状态的 tensor 产品）称为 "放大状态";这两个 qubits 称为[*放大*](https://en.wikipedia.org/wiki/Quantum_entanglement)。  由于不能将量程状态视为单一 qubit 状态的 tensor 产品，因此，状态保存的信息并不局限于每个 qubits。  相反，该信息在两个状态之间的关联中以非本地方式存储。  此非区域信息是针对传统计算的量程计算的主要区别功能之一，并且对于大量的量程协议（包括[量程 teleportation](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation)和[量程错误更正](xref:microsoft.quantum.libraries.error-correction)）非常重要。

## <a name="measuring-two-qubit-states"></a>度量 Qubit 状态 ##
测量 qubit 状态与 qubit 度量非常类似。 测量状态

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ alpha_{10} \\\\ alpha_ \{11} \end{bmatrix} $ $

生成 $0 $ with probability $ | \ alpha_{00}| ^ $2、$1 $ with probability $ | \ alpha_{01}| ^ $2、$10 $ with probability $ | \ alpha_{10}| ^ $2 和 $11 $ with probability $ | \ alpha_{11}| ^ $2。 变量 $ \ alpha_{00}，\ alpha_{01}，\ alpha_{10}，$，$ \ alpha_{11}$ 被特意命名为明文进行此连接。 完成度量后，如果结果为 $0 $，则 qubit 系统的量程状态将折叠，并且现在

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}。
$$

还可以只测量一个 qubit 为两 qubit 的量程状态。 在仅测量其中一个 qubits 的情况下，度量值的影响将稍有不同，因为整个状态不会折叠为计算基础状态，而只是折叠为一个子系统。  换句话说，在这种情况下，只测量一个 qubit 只会折叠其中一个子系统，而不是全部。  

若要查看这一点，请考虑测量以下状态的第一个 qubit，这是通过对两个 qubits 上 $H 的 $ $ 初始设置为 "0" 状态而形成的： $ $ H ^ {\otimes 2} \left （\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \right） = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 & 1 & 1 & \\\\ 1 & 1 &1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ 结束 {bmatrix} = \frac{1}{2}\\\\\\1 \\\\1 \\ & 1 \ 结束 {bmatrix} \mapsto \begin{cases}\text{outcome} = 0{1}\frac{2}{\sqrt\\} \begin{bmatrix}1 \\\\1 \\\\0 \\\\0 \end{bmatrix}\\ \text{outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\\\\\\\1 \\\\1 \end{bmatrix} \\ \end{cases}。\\\\
$ $ 这两个结果的发生率均为50%。  这两者的结果50% 的概率可能是 intuited 的，这是因为初始量程状态向量在第一个 qubit 上的交换 $0 $1 $ 下是固定的。

用于度量第一个或第二个 qubit 的数学规则非常简单。  如果我们允许 $e _k $ 是 $k ^ {\rm th} $ 计算基础向量，并允许 $S $ 为所有 $e $ 的集合，以使 qubit 的值为 _k $ 的值 $1 $。  例如，如果对度量第一个 qubit 感兴趣，则 $ $S $ 将包含 $e _2 \ http-equiv $10 和 $e _3 \ http-equiv $11。  同样，如果我们对第二个 qubit 感兴趣 $S $ 将包含 $e _1 \ http-equiv $1 和 $e _3 \equiv $11。  那么，将所选 qubit 测量为 $1 $ 的概率为状态向量 $ \psi $

$ $ P （\text{outcome} = 1） = \ sum_ {e_k 集} S} \psi ^ \dagger e_k e_k ^ \dagger \psi。
$$

由于每个 qubit 度量仅可产生 $0 $ 或 $1 $，因此 $0 度量值为的概率只是 $1-P （\text{outcome} = 1） $。  这就是我们只为衡量 $1 $ 的概率显式提供公式的原因。

此类测量对状态的操作可以数学表示为

$ $ \psi \mapsto \frac{\ sum_ {e_k 集} S} 中的 \text{e_k e_k ^ \dagger \psi}{\sqrt{P （\text{outcome} = 1）}}。
$$

如果度量值为零，则谨慎读者可能会担心发生了什么情况。  尽管在此情况下，结果状态在技术上是未定义的，但我们永远不需要担心此类不测，因为概率为零！


如果将 $ \psi $ 指定为上面给定的统一状态向量，并对度量第一个 qubit 感兴趣，则 

$ $ P （第一个 qubit 的 \text{measurement} = 1） = （\psi ^ \dagger e_2）（e_2 ^ \dagger \psi） + （\psi ^ \dagger e_3）（e_3 ^ \dagger \psi） = | e_2 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2。
$$

请注意，这只是测量结果的两个概率的总和，$10 $ 和 $11 $ 就是要测量的所有 qubits。
对于我们的示例，此值的计算结果为

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ 结束 {bmatrix} \ 开始 {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 0 & 1 \ end {bmatrix} \ 开始 {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 = \frac{1}{2}。
$$

这完全匹配了我们的直觉告诉我们的概率。  同样，可以将状态编写为

$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ end {bmatrix} $ $

再次遵循我们的直觉。

## <a name="two-qubit-operations"></a>Qubit 操作
与 qubit 情况一样，任何单一转换都是对 qubits 的有效操作。 通常，$n $ qubits 上的单一转换是一个大小为 $ 2 ^ n \times 2 ^ n $ 的矩阵 $U $ （因此它作用于大小为 $ 2 ^ n $ 的矢量），以便 $U ^{-1} = U ^ \dagger $。 例如，CNOT-CONTAINS （受控-NOT）门是一种常用的 qubit 门，由以下单一矩阵表示：

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \\\ 0 \end{bmatrix} $ $\\

我们还可以通过在两个 qubits 上应用 qubit 入口来形成两 qubit 入口。 例如，如果我们应用入口 

$ $ \begin{bmatrix} a b\\\\ c \ d \end{bmatrix} $ $

and

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

对于第一个和第二个 qubits，这相当于应用其 tensor 产品指定的 qubit 单一项： $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin{bmatrix} ae \ bf \ bh \\\\ ce \ cf \ de \ df \\\\ cg \ ch \ dg \ dh \end{bmatrix}. $ $，所以我们可以通过采用一些已知的 qubit 入口的 tensor 产品来形成两 qubit 入口。\\\\ Qubit 入口的一些示例包括 $H \otimes H $、$X \otimes \boldone $ 和 $X \otimes Z $。

请注意，尽管任意两个 qubit 入口通过 tensor 产品来定义两 qubit 入口，但反之并不成立。 并非所有 qubit 入口都可以编写为 qubit 入口的 tensor 产品。  此类入口称为*entangling*入口。 Entangling 入口的一个示例是 CNOT-CONTAINS 入口。

受控-not 入口后面的直觉可以通用化为任意入口。  通常，受控制的入口是作为标识（即它没有操作）的入口，除非特定 qubit 为 $1 $。  我们在这种情况下，在 qubit $x 为 $ \Lambda 的上（如 $\_x （U） $）表示控制单一的受控单一。  例如，$ \ Lambda_0 （U） e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ 和 $ \Lambda\_0 （U） e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $，其中 $e\_$0 和 $e\_$1 是对应于值 $0 $ 和 $1 $ 的单个 qubit 的计算基础向量。  例如，请考虑下面的受控 $Z $ 门，然后我们可以将其表示为 $ $ \Lambda\_0 （Z） = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = （\boldone\otimes H） \operatorname{CNOT} （\boldone\otimes H）。
$$

有效地构建受控 unitaries 是一项重大挑战。  实现此操作的最简单方法就是构建一个受控版本的基本入口数据库，并将原始单一操作中的每个基本入口替换为其受控对应项。  这通常是一种浪费的浪费，通常可用于将几个入口替换为受控版本来实现同样的效果。  出于此原因，我们提供了一种简单的方法来执行控制或允许用户定义单一受控版本（如果已知优化的手动优化版本）的功能。

还可以使用传统信息控制入口。  例如，经典控制的不是一个典型的非入口，但仅当传统位为 $1 $ 而不是一个量程位时，它才适用。  从这种意义上讲，可以将经典控制的入口看作是量程代码中的 if 语句，其中的门仅应用于代码的一个分支。


就像在 qubit 情况下，如果有任何 $ 4 \ $4 的入口矩阵可通过此集中的一项产品来逼近，则这两个 qubit 入口集是通用的。
通用入口集的一个示例是 Hadamard 门、T 门和 CNOT-CONTAINS 入口。 通过采用这些入口的产品，我们可以将两个 qubits 上的任何单一矩阵近似。

## <a name="many-qubit-systems"></a>多 Qubit 系统
我们按照两个 qubit 案例中所述的完全相同的模式，从较小的系统生成 qubit 的量程状态。  此类状态是通过构建较小状态的 tensor 产品生成的。  例如，请考虑对量程计算机中的位字符串 $1011001 $ 进行编码。  我们可以将此编码为

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}。
$$

量程入口的工作方式完全相同。  例如，如果想要对第一个 qubit 应用 $X $ 门，然后在第二个和第三个 qubits 之间执行 CNOT-CONTAINS，我们可能会将此转换表示为

\begin{align} & （X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone） \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes\begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001。
\end{align}

在许多 qubit 的系统中，通常需要分配并取消分配充当量子计算机的临时内存的 qubits。  此类 qubit 称为 ancilla。  默认情况下，我们假设 qubit 状态初始化为在分配时 $e _0 $。  接下来，我们会进一步假定在取消分配之前再次返回 $e _0 $。  这一假设非常重要，因为如果 ancilla qubit 在被解除分配后会与另一个 qubit 注册放大，则解除分配的过程将损坏 ancilla。  出于此原因，我们总是会假设此类 qubits 在发布之前会恢复到其初始状态。

最后，尽管需要将新入口添加到设置为实现两个 qubit 量程计算机的通用量程计算的入口，但在多 qubit 情况下，不需要引入新的入口。  Cnot-contains $、$T $ 和这两个平台都形成了许多 qubits 上的通用门集，因为任何常规的单一转换都可以分解为一系列的 qubit 旋转。 $H  接下来，我们可以利用针对双 qubit 案例开发的理论，并在有许多 qubits 时再次使用。

虽然我们一直在使用的线性代数表示法可以用来描述多 qubit 状态，但随着状态的增加，这会变得越来越繁琐。  例如，对于长度为7位字符串的结果列向量为 $128 $ 维，这使得使用前面所述的表示法来表示它。  出于此原因，我们接下来在量程计算中显示一个常见的表示法，使我们能够简明地描述这些三维向量。
