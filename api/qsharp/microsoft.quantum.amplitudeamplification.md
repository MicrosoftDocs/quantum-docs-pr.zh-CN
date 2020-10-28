---
uid: Microsoft.Quantum.AmplitudeAmplification
title: AmplitudeAmplification 命名空间
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: 09c29bd9d0648bb8652051ad97ceca6ef6557df3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700101"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>AmplitudeAmplification 命名空间

此命名空间包含用于执行振幅放大的函数和操作。



## <a name="description"></a>说明

采用部分反射的在意波幅放大是在此处实现的最常见的波幅放大形式。

这是通过操作 AmpAmpObliviousByReflectionPhases 调用的。

这有两个寄存器： `ancillaRegister` 和 `systemRegister` 。

这会接受两个 oracles，这种类型的反射 `ReflectionOracle` 只对 `ancillaRegister` 寄存器执行操作。

这就接受了一种 `ObliviousOracle` 在两个寄存器上共同操作的类型的 oracle 特殊在意波幅放大。

假定输入状态为 `ancillaRegister` 第一个反射运算符的唯一 $-$1 eigenstate，$I-2 \ 票证 {s} \ 寄存器 {s} $。

反射目标量程状态的反射通常是通过假定访问从计算基础 $ \ket{0\cdots 0} $ 准备该状态的 oracle 来实现的。

对于这些 oracles，我们的惯例需要两个注册：一个 qubit `flagQubit` 寄存器，另一个寄存器用于 ancillaRegister 寄存器上的其他所有内容。

类型为的 oracle `StateOracle` 在两个寄存器上共同操作， {1} `flagQubit` 用一些真实幅度来创建由寄存器中的 $ \ket $ 标记的目标状态。

`ReflectionOracle`此标记状态的反射是由操作生成的 `TargetStateReflectionOracle` 。

`ReflectionOracle`有关输入状态的反射将 `ancillaRegister` 由反 StateOracle 生成，然后使用 ReflectionStart ( # A1 反射 $ \ket{0\cdots 0} $。

类型为的 oracle `DeterministicStateOracle` 对 `qubitState` 寄存器进行操作，以完全不带标志的方式创建目标状态。

`AmpAmpObliviousByOraclePhases` 是在意波幅放大的版本，它接受 oracles `StateOracle` ， `ObliviousOracle` 而不是反射。

请注意，振幅放大是在意波幅放大的一种特殊情况，其中， `ObliviousOracle` 是标识运算符，不存在任何系统 qubits，即 `systemRegister` 为空。

此操作通过操作和调用 `AmpAmByReflectionPhases` `AmpAmpByOraclePhases` 。

Grover 搜索标准情况下的部分反射阶段由函数 AmpAmpPhasesStandard 提供。

例如，我们有以下依赖项： AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases。