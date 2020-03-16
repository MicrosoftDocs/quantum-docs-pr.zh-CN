---
title: 问答中的量程算法#
description: 了解基本的量程计算算法，包括波幅放大、傅立叶转换、Draper 和 Beauregard 添加器以及相位估算。
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 8b8a9019e8bc419f42b0c6f7558354d19a157917
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402844"
---
# <a name="quantum-algorithms"></a>量程算法 #

## <a name="amplitude-amplification"></a>振幅放大 ##

*振幅放大*是量程计算的一项基本工具。 这是一种基本的概念，即 Grover 的搜索、幅度估算和许多量程机器学习算法。  有很多变体，在 Q # 中，我们提供了一个基于在意波幅放大的通用版本，并提供了部分反射，以允许最广泛的应用程序区域。

振幅放大的中心思想是通过执行一系列反射来放大所需结果的概率。  这些反射会使初始状态更接近所需的目标状态，通常称为标记的状态。  具体来说，如果将初始状态测量为标记状态的概率为 $ \sin ^ 2 （\theta） $，然后在应用振幅放大后 $m $ 次，则成功的概率为 $ \sin ^ 2 （（2m + 1） \theta） $。  这意味着，如果 $ \theta = \ pi/[2 （2n + 1）] $\\$n $ 的某些值，则幅度放大功能能够提高 $n $ 迭代幅度放大后成功 $100% $ 的概率。  由于 $ \theta = \sin ^{-1}（\sqrt{\Pr （success）}） $ 这意味着，要明确获取成功所需的迭代次数几率低于需要使用随机抽样来确定标记状态的不确定状态所需的次数。

振幅放大的每个迭代都需要指定两个反射运算符。 具体而言，如果 $Q $ 是振幅放大循环访问，$P _0 $ 是在初始子空间上的一个投影仪运算符，并且 $P _1 $ 就是投影仪到标记的子空间，然后 $Q =-（\boldone-2P_0）（\boldone-2P_1） $。  回忆一下，投影仪是 Hermitian 运算符，其中包含本征值 $ + $1 和 $0 $，因此 $ （\boldone 2P_0） $ 是单一的，因为它具有作为 unity 根的本征值（在本例中为 $ \pm $1）。 作为示例，请考虑使用初始状态 $H ^ {\otimes n} \ket{0}$ and 标记状态 $ \ket{m} $，$P _0 = H ^ {\otimes n} \ket{0}\bra{0}H ^ {\otimes n} $ 和 $P _1 = \ket{m}\bra{m} $ 的情况。  在幅度放大的大多数应用程序中 $P _0 $ 将成为初始状态的投影仪，这意味着 $P _0 = \boldone-2 \ 票证 {\ psi} \ 寄存器 {\ psi} $ for a vector $ \ket{\psi} $;但对于在意波幅 amplication $P _0 $ 通常投影到许多量程状态（即，$P _0 $ 的 $ + $1 eigenvalue 的重数大于 $1 $）。

振幅放大后的逻辑直接在 $Q $ 的本征分解之后。  具体而言，$Q $ 的的本征向量 $ 表明初始状态具有非零支持可以显示为 $P _0 $ 和 $P _1 $ 的 $ + $1 本征向量的线性组合。  具体而言，振幅放大的初始状态（假设它为 $P _0 $ 的 $ + $1 eigenvector）可以编写为 $ $ \ket{\psi} = \frac{-i}{\sqrt{2}} \left （e ^ {i\theta} \ 票证 {\ psi_} \ i\theta {\ psi_-} 票证），$ $ （其中 $ \ket{\ psi_ \pm} $）本征向量 $Q $ with 本征值 $e ^ {\pm 2i \ theta} $，并且仅支持 $P 本征向量 $ 和 $P _1 $ 的 $ + $1 _0。  本征值 $e 是 ^ {\pm i \theta} $ 这一事实意味着运算符 $Q $ 在两个投影仪指定的二维子空间中执行旋转，而初始状态则为 ""。  这就是 $m $ $Q $ 迭代的原因是 $ \sin ^ 2 （[2m + 1] \theta） $ 的成功概率。

这一问题的另一个有用的属性是 eigenvalue $ \theta $ 直接与初始状态要标记的概率相关，在 $P 这种情况下，只会将一个投影仪置于初始状态。  由于 $Q $ 的 eigenphases 是 $ 2 \ theta = 2 \ sin ^{-1}（\sqrt{\Pr （success）}） $，因此，如果我们将阶段估算应用到 $Q $，则我们可以了解单一量程过程成功的概率。  这很有用，因为它需要几率更少的量程过程应用程序，以了解与其他情况下的成功概率。

Q # 将振幅放大引入为在意波幅放大的专用化。  在意波幅放大盈利此名字对象，因为投影仪到初始 eigenspace 无需投影仪到初始状态。  从这种意义上讲，该协议在意初始状态。  在意波幅放大的关键应用是单一 Hamiltonian 模拟方法的一些*线性组合，其中*初始状态是未知的，但会在模拟协议中与 ancilla 注册放大。  如果将此 ancilla 寄存器测量为固定值（如 $0 $），则此类模拟方法会将所需的单一转换应用到剩余的 qubits （称为系统注册）。  但是，所有其他测量结果都会导致故障。  在意波幅放大允许使用以上推理将此度量值的成功提升为 $100\\% $。  而且，普通幅度放大对应于系统注册为空的情况。  这就是 Q # 使用在意波幅放大子例程的原因。

常规例程（`AmpAmpObliviousByReflectionPhases`）具有两个注册 `ancillaRegister` 和 `systemRegister`。 它还接受两个 oracles 来实现必要的反射。 `ReflectionOracle` 仅在 `ancillaRegister` 上起作用，而 `ObliviousOracle` 在两个寄存器上共同操作。 `ancillaRegister` 的输入必须初始化为第一个反射运算符 $ \boldone-2P_1 $ 的第1个 eigenstate。

通常，oracle 在计算基础 $ \ket{0...0} $ 中准备状态。 在我们的实现中，有一个 qubit （`flagQubit`）的 `ancillaRegister` consistes，用于控制 `stateOracle` 和所需的其余 ancillas。 当 `flagQubit` 为 $ \ket{1}$ 时应用 `stateOracle`。

还可以通过调用 `AmpAmpObliviousByOraclePhases`提供 oracles `StateOracle` 和 `ObliviousOracle` 而不是反射。

如前所述，传统的振幅放大只是这些例程的一种特殊情况，其中 `ObliviousOracle` 是标识运算符，并且没有系统 qubits （即 `systemRegister` 为空）。 如果要获取部分反射的阶段（例如，对于 Grover 搜索），可以使用函数 `AmpAmpPhasesStandard`。 有关 Grover 算法的示例实现，请参阅 `DatabaseSearch.qs`。

我们将 qubit 轮换阶段与反射运算符阶段相关联[，如 G.H. Low，语](https://arxiv.org/abs/1707.05391)中所述。 使用的固定点阶段在[Yoder、low 和语](https://arxiv.org/abs/1409.3305)以及[low、Yoder 和语](https://arxiv.org/abs/1603.03996)的阶段中进行了详细说明。

对于背景，你可以从[标准幅度放大](https://arxiv.org/abs/quant-ph/0005055)开始，转到[在意波幅放大](https://arxiv.org/abs/1312.1414)简介，最后展示为[Low 和语](https://arxiv.org/abs/1610.06546)。 [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf)提供了这一整个区域（与 Hamiltonian 模拟相关）的良好概述演示。

## <a name="quantum-fourier-transform"></a>量程傅立叶转换 ##

傅立叶转换是一种古典型分析工具，与量程计算一样重要。
此外，*量程傅立叶转换*（QFT）的效率远远超过了传统计算机上可能的功能，因此，在设计量程算法时，首先要选择的工具之一。

作为 QFT 的大致通用化，我们提供了 <xref:microsoft.quantum.canon.approximateqft> 操作，该操作允许通过修剪旋转（对所需的算法准确性并不是绝对必需的）进行进一步的优化。
大致的 QFT 要求 dyadic $Z $-旋转操作 <xref:microsoft.quantum.intrinsic.rfrac> 和 <xref:microsoft.quantum.intrinsic.h> 操作。
输入和输出假设编码为大字节序编码---也就是说，具有索引 `0` 的 qubit 在二进制整数表示形式的最左端（最高）位进行编码。
这与[票证表示法](xref:microsoft.quantum.concepts.dirac)一致，因为状态 $ \ket 中的三个 qubits 的寄存器{100}$ 对应于 $q _0 $ 处于状态 $ \ket{1}$，同时 $q _1 $ 和 $q _2 $ 都处于状态 $ \ket{0}$。
近似值参数 $a $ 确定 $Z $ 旋转的修剪级别，即 $a \in [0 ... n] $。
在这种情况下，所有 $Z $-循环 $ 2 \ pi/2 ^ k $，其中 $k > $ 将从 QFT 线路中删除。
已知 $k \ge \ log_2 （n） + \ log_2 （1/\epsilon） + $3。 一个可以绑定 $\\|\operatorname{QFT}-\operatorname{AQFT} \\|< \epsilon $。
此处 $\\| \cdot\\| $ 是运算符标准，这种情况下，这种情况下是 $ （\operatorname{QFT}-\operatorname{AQFT}）（\operatorname{QFT}-\operatorname{AQFT}） ^ \dagger $ 的最大[eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced)的平方根。

## <a name="arithmetic"></a>算术 ##

正如算术在传统计算中扮演中心角色一样，在量程计算中也是必不可少的。  诸如选定的分解算法、量程模拟方法以及许多 oracular 算法等算法依赖于一致的算术运算。  用于在量程创建线路上进行算法生成的大多数方法。  最简单的添加程序会将传统输入 $b $，并将值添加到包含整数 $ \ket{a} $ 的量程状态。  从数学上来说，\operatorname{Add} 的 "提供程序" （我们表示 "用于经典 $b 输入的 $ （b） $"）具有属性，该属性

$ $ \operatorname{Add} （b） \ket{a} = \ket{a + b}。
$ $ 这一基本的增加，incrementer 比一个增加程序更多。
它可以通过 $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b} 转换为具有两个量程输入的合并程序，$ $ 使用添加器的 $ 受控应用程序 \begin{align} \operatorname{Add} \Ket{a} \ket{b} & = \Lambda\_{a\_0} \left $n （\operatorname{Add} （1） \right） \Lambda\_{a\_1} \left （\operatorname{Add} （2） \right） \Lambda\_{a\_2} \left （\operatorname{Add} （4） \right} \cdots \Lambda （\o {Add} （{{\right}}）） \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}，\end{align} $n $ 位整数 $a $ and $b $，加法取模 $ 2 ^ n $。\_\_  请记住，notation $ \Lambda\_x （A） $ 将 qubit $x $ 作为控件的操作的受控版本 $A 引用。

同样，经典受控乘法（这是选定的分解算法必需的模块化形式）可以通过使用一系列类似的受控添加来执行： \begin{align} \operatorname{Mult} （a） \ket{x}\ket{b} & = \Lambda\_{x\_0} \left （\operatorname{Add} （2 ^ 0 a） \right） \Lambda\_{a\_1} \left （\operatorname{Add} （2 ^ 1a） \right） \Lambda\_{a\_2} \left （\operatorname{Add} （2 ^ 2 {n-1}} \left （\operatorname{Add} （{2 ^ {n-1}} a） \right） \ket{x}\ket{b} \\\\ & = \ket{x}\ket{b + ax}。\_\_
\end{align} 在量程计算机上有一个个很微妙，你可能会注意到上面 $ \operatorname{Mult} $ 的定义。  与此不同，此线路的量程版本将输入的产品存储在辅助寄存器中而不是输入寄存器中。  在此示例中，寄存器用值 $b $ 进行初始化，但它通常会开始将值保留为零。  这在中是必需的，因为一般情况下，一般 $a $ 和 $x $ 之间没有乘法逆。  由于所有量程操作（节省度量值）都是可逆的，因此我们需要保留足够的信息来反转乘法。  出于此原因，结果将存储在单独的数组中。  在单独的寄存器中保存不可逆操作（如乘法）输出的这一技巧称为 Charlie Bennett 后的 "Bennett 技巧"，它是可逆计算和量程计算的一项基本工具。

已建议使用许多量程线路进行添加，并且每个线路在 qubits （空间）数和所需的入口操作（时间）数方面探讨了不同的折衷。  我们将在以下两个高空间高效的添加器（称为 Draper 的 Beauregard 和的）中查看。

### <a name="draper-adder"></a>Draper ###

Draper 添加是最巧妙的量程添加器之一，因为它直接调用量程属性以执行添加。  Draper 加载程序背后的见解是，可以使用傅立叶变换将相位移位转换成移位。  接下来，通过应用傅立叶变换，应用适当的阶段移位，然后撤消傅立叶转换，可以实现一个转换程序。  与其他许多已建议的添加器不同，Draper 的创建程序显式使用通过量程傅立叶转换引入的量程效果。  它没有典型的传统对应项。  下面给出了 Draper 提供的特定步骤。

假设您有两个 $n $ bit qubit 寄存器将整数 $a $ 和 $b $，然后针对所有 $a $ $ $ \operatorname{QFT}\ket{a} = \frac{1}{\sqrt{2 ^ n}} \sum\_{j = 0} ^ {2 ^ n-1} e ^ {i2\pi （aj）/2 ^ n} \ket{j}。
$ $ 如果我们定义 $ $ \ket{\phi\_k （a）} = \frac{1}{\sqrt{2}} \left （\ket{0} + e ^ {i2\pi a/2 ^ k} \ket{1} \right），$ $ 则在某个代数后，可以看到 $ $ \operatorname{QFT}\ket{a} = \ket{\phi\_1 （a）} \otimes \cdots \otimes \ket{\phi\_n （a）}。
$ $ 要执行转换程序的路径在观察到输入的总和可以写为 $ $ \ket{a + b} = \operatorname{QFT} ^{-1}\ket{\phi\_1 （a + b）} \otimes \cdots \otimes \ket{\phi\_n （a + b）} 后，就变得清楚。
$ $ $B $ 和 $a $ 的整数，则可以通过使用 $b $ 的位作为控件，在分解中的每个 qubits 上执行受控制的阶段旋转。

请注意，对于任何整数 $j $ 和实数 $x $，$e ^ {i2\pi （x + j）} = e ^ {i2\pi x} $，可以进一步简化此扩展。  这是因为，如果在圆圈中旋转 $ 360 ^ {\circ} $ 度数（$ 2 \ pi $ 弧度），则最终会精确到开始处。  因此 $e ^ {i2\pi x} $ $x $ 的唯一重要部分是 $x $ 的小数部分。  具体而言，如果我们的二进制扩展形式 $x = y +0\_0x\_2 \ ldots x\_n $，则 $e ^ {i2\pi x} = e ^ {i2\pi （0）。 x\_0x\_2 \ ldots x\_{n-1}）} $，因此 $ $ \ket{\phi\_k （a + b）} = \frac{1}{\sqrt{2}} \left （\ket{0} + e ^ {i2\pi [a/2 ^ k +0\_k\ldots b\_1]} \ket{1} \right）。 $ $ 这意味着，如果通过增加 $ tensor $ 的傅立叶转换的扩展中的每个 \ket{a} 因素来执行加法运算，随着 $k $ 减小，旋转收缩的数目。  这极大地减少了增加插件所需的量程入口数。  我们指出了傅立叶变换、相位加法和反傅立叶变换步骤，这些步骤包含 Draper 添加程序作为 $ \operatorname{QFT} ^{-1} \left （\phi\\\!\operatorname{ADD}\right） \operatorname{QFT} $。 下面显示了使用这种简化实现整个过程的量程线路。

![显示为线路关系图的 Draper](~/media/draper.svg)

线路中的每个受控 $e ^ {i2 \ pi/k} $ 入口都指受控的阶段入口。  此类入口的属性在其作用的 qubits 对上，$ \ket{00}\mapsto \ket{00}$ 但 $ \ket{11}\mapsto e ^ {i2 \ pi/k} \ 票证{11}$。  利用此线路，我们可以使用除存储输入和输出所需的其他 qubits 以外的其他任何功能来执行添加。

### <a name="beauregard-adder"></a>Beauregard ###

Beauregard 添加程序是一个量程模块化添加程序，它使用 Draper 添加程序来对任意值为正整数 $N $ 执行加法取模 $N $。  量程模块化添加器（如 Beauregard 外接程序）的重要性，就是在选定算法中用于因式分解的模块求幂步骤中，其使用范围很大。  量程模块化外接程序对量程输入 $ \ket{b} $ 和经典输入 $a $ 具有以下操作，其中 $a $ 和 $b $ 被承诺为整数 mod $N $，这意味着它们处于 [0，\ldots，N-1] $ 的间隔。

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{cases} \ket{b + a}，& b + a < N\\\\ \ket{b + a-N}，& （b + a） \ge N \end{cases}。
$$

Beauregard 添加使用 Draper 添加，或更具体的 $ \phi\\\!\operatorname{ADD} $，以在阶段中添加 $a $ 和 $b $。  然后，它将使用相同的操作来确定是否 $a + b < N $，方法是在 $a + b-N < 0 $ 减 $N $ 和测试。  线路将此信息存储在辅助 qubit 中，然后在 $a + b < N $ 时，将 $N $ 返回寄存器。  然后，它会通过 uncomputing 此辅助位来结束（需要此步骤以确保在调用此项补充后可以取消分配 ancilla）。  下面给出了 Beauregard 提供程序的线路。

![显示为线路关系图的 Beauregard](~/media/beau.svg)

此处的入口 $ \Phi\\\!\operatorname{ADD} $ 采用与 $ \Phi\\\!\operatorname{ADD} $ 相同的格式，但在此上下文中，输入为经典而不是量程。  这允许将 $ \Phi 中的受控阶段\\\!\operatorname{ADD} $ 替换为阶段入口，然后可以将该入口编译成更少的操作，减少了执行程序所需的 qubits 数量和入口数。

有关更多详细信息，请参阅[Roetteler、Beth](http://doi.org/10.1007/s00200-008-0072-2 )和[Coppersmith](https://arxiv.org/abs/quant-ph/0201067)。

### <a name="quantum-phase-estimation"></a>量子相位估计 ###

量程傅立叶转换的一个特别重要的应用是了解单一运算符（称为*阶段估算*的问题）的本征值。
假设单一 $U $ 和状态 $ \ket{\phi} $，$ \ket{\phi} $ 是包含未知 eigenvalue $ \phi $ 的 $U $ 的 eigenstate，\begin{equation} U\ket {\ phi} = \phi\ket{\phi}。
\end{equation} 如果仅有权访问作为 oracle $U $，则可以通过使用应用于受控操作目标的 $Z $ 旋转传播回控件来了解阶段 $ \phi $。

假设 $V $ 是 $U $ 的受控应用程序，因此 \begin{align} V （\ket{0} \otimes \ket{\phi}） & = \ket{0} \otimes \ket{\phi} \\\\ \textrm{and} V （\ket{1} \otimes \ket{\phi}） & = e ^ {i \phi} \ket{1} \otimes \ket{\phi}。
然后，\end{align}，通过线性，\begin{align} V （\ket{+} \otimes \ket{\phi}） & = \frac{（\ket{0} \otimes \ket{\phi}） + e ^ {i \phi} （\ket{1} \otimes \ket{\phi}）} {\sqrt{2}}。
\end{align} 我们可以收集术语来查找 \begin{align} V （\ket{+} \otimes \ket{\phi}） & = \frac{\ket{0} + e ^ {i \phi} \ket{1}} {\sqrt{2}} \otimes \ket{\phi} \\\\ & = （R_1 （\phi） \ket{+}） \otimes \ket{\phi}，\end{align}，其中 $R _1 $ 是 <xref:microsoft.quantum.intrinsic.r1> 操作应用的那个。
换句话说，应用 $V $ 的影响与将 $R _1 $ 应用于未知角度完全相同，即使我们仅有权访问作为 oracle $V $。
因此，对于本文的其余部分，我们将根据 $R _1 （\phi） $ （通过使用所谓的*阶段 kickback*来实现）讨论阶段估算。

由于在此过程后，控件和目标注册仍处于 untangled 状态，因此，我们可以将 $ \ket{\phi} $ 作为 $U ^ $2 的受控应用程序的目标，以便在州 $R _1 （2 \phi） \ket{+} $ 中准备第二个控制 qubit。
继续以这种方式，我们可以获取形式为 \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 （2 ^ j \phi） \ket{+} \\\\ & \propto \ bigotimes_ {j = 0} ^ {n} \left （\ket{0} + \exp （i 2 ^ {j} \phi） \ket{1}\right） \\\\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp （i \phi k） \ket{k} \end{align}，其中 $n $ 是我们需要的精度位数。并且，我们已使用 ${} \propto $ {}$ 来指示我们抑制了 $1/\sqrt 的规范化系数{2 ^ n} $。

如果我们假设 $ \phi = 2 \pi p/2 ^ k $ 用于整数 $p $，则我们会将其识别为 $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots . p_n} $，其中 $p _j $ 是 $2 \textrm{th}} \pi $ 的 $j ^ {\phi $ 位。
通过应用 "量程傅立叶转换" 的 adjoint，我们将获得编码为量程状态的阶段的二进制表示形式。

在 Q # 中，这是由 <xref:microsoft.quantum.characterization.quantumphaseestimation> 操作实现的，该操作采用 <xref:microsoft.quantum.oracles.discreteoracle> 实现 $U ^ m $ 的应用程序作为 $m $ 的正整数函数。
