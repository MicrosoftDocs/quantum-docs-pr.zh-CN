---
title: 量子计算词汇表
description: 量子计算中使用的常用术语、操作和对象的词汇表。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482225"
---
# <a name="quantum-computing-glossary"></a>量子计算词汇表

## <a name="adjoint"></a>伴随

操作的复杂共聚[转换。](xref:microsoft.quantum.glossary#operation) 对于实现[单一](xref:microsoft.quantum.glossary#unitary-operator)运算符的操作，邻接是操作的反向，由剑符号表示。 例如，如果操作`U`表示单一运算符 $U$，则`Adjoint U`表示 $U\agger$。 有关详细信息，请参阅[Ad和](xref:microsoft.quantum.language.file-structure#adjoint)

## <a name="ancilla"></a>安西拉

用作量子计算机的临时内存并根据需要分配和取消分配的[qubit。](xref:microsoft.quantum.glossary#qubit)  有关详细信息，请参阅[多个量子位](xref:microsoft.quantum.concepts.multiple-qubits)。

## <a name="bell-state"></a>贝尔州

四个特异性最大[纠缠](xref:microsoft.quantum.glossary#entanglement)[的量子态](xref:microsoft.quantum.glossary#quantum-state)之一，两个量子位。 这四种状态定义 $ket_beta_{i}= （\mathbb_I__otimes X_iZ_j） （\ket{00} ={11}\ket） /{2}\sqrt $。 贝尔状态也称为[EPR 对](xref:microsoft.quantum.glossary#epr-pair)。

## <a name="bloch-sphere"></a>布洛赫球体

单[量子位](xref:microsoft.quantum.glossary#qubit)[量子态](xref:microsoft.quantum.glossary#quantum-state)的图形表示形式，作为三维单元球体的点。 有关详细信息，请参阅使用[Bloch 球体可视化 Qubit 和变换](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)。

## <a name="callable"></a>调用

Q# 语言中的[操作](xref:microsoft.quantum.glossary#operation)或[函数](xref:microsoft.quantum.glossary#function)。 有关详细信息，请参阅[操作和函数类型](xref:microsoft.quantum.language.type-model#operation-and-function-types)。

## <a name="clifford-group"></a>克利福德集团

占据[布洛赫球体的](xref:microsoft.quantum.glossary#bloch-sphere)八进制和[保利运算符](xref:microsoft.quantum.glossary#pauli-operators)的效应排列的一组操作。 其中包括[$X$、$Y$、$Z$、$H](xref:microsoft.quantum.intrinsic.x)[美元](xref:microsoft.quantum.intrinsic.h)和[$S美元](xref:microsoft.quantum.intrinsic.s)。 [$Y$](xref:microsoft.quantum.intrinsic.y) [$Z$](xref:microsoft.quantum.intrinsic.z)

## <a name="controlled"></a>控制

将一个或多个[量子位](xref:microsoft.quantum.glossary#qubit)作为目标操作的启用器的量子[运算](xref:microsoft.quantum.glossary#operation)。 有关详细信息，请参阅[受控](xref:microsoft.quantum.language.type-model#controlled)。

## <a name="dirac-notation"></a>狄拉克符号

简化[量子态](xref:microsoft.quantum.glossary#quantum-state)表示的符号速记，也称为*胸带*符号。  *bra*部分表示行矢量，例如 ${bra}A} } [开始]bmatrix} A[1]& A{2}\end_bmatrix_$和*ket*部分表示列矢量，${ket{B} = {开始}bmatrix} \\ \\ B{1}B}2}{2}=$$。 有关详细信息，请参阅[Dirac 符号](xref:microsoft.quantum.concepts.dirac)。

## <a name="eigenvalue"></a>特征

给定变换的[eigenvector](xref:microsoft.quantum.glossary#eigenvector)大小因转换的应用而改变的因子。  给定一个平方矩阵$M$和一个 eigenvector$v$，然后$Mv = cv$，其中$c$是 eigen值，可以是任何参数的复杂数字。 有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="eigenvector"></a>艾根矢量

方向因给定变换而保持不变，其幅度由对应于该矢量的[eigen 值](xref:microsoft.quantum.glossary#eigenvalue)的因子改变的矢量。 给定一个平方矩阵$M$和一个 eigenvalue $c$，然后$Mv = cv$，其中$v$是矩阵的 eigenvector，可以是任何参数的复杂数字。 有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="entanglement"></a>纠缠

量子粒子，如[量子位](xref:microsoft.quantum.glossary#qubit)，可以连接或*纠缠*，以至于它们不能相互独立地描述。 即使它们相距无限远，它们的测量结果也是相互关联的。 纠缠对于[测量](xref:microsoft.quantum.glossary#measurement)量子位[的状态](xref:microsoft.quantum.glossary#quantum-state)至关重要。  有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="epr-pair"></a>EPR 对

四个特异性最大纠缠[的量子态](xref:microsoft.quantum.glossary#quantum-state)之一，两[个量子位](xref:microsoft.quantum.glossary#qubit)。 这四{1}种状态定义 $ket\beta_[ij]= （\mathbb \otimes X_iZ_j） （\ket{00} {11}= \ket{2}） / \sqrt $。 EPR 对也称为[贝尔状态](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>演化

[量子状态](xref:microsoft.quantum.glossary#quantum-state)如何随时间而变化。 有关详细信息，请参阅[矩阵指数](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)。

## <a name="function"></a>函数
Q# 语言中纯经典（非量子）的子例程类型。 虽然函数在量子算法中使用，但它们不能对[量子位](xref:microsoft.quantum.glossary#qubit)或调用操作执行[操作](xref:microsoft.quantum.glossary#operation)。 有关详细信息，请参阅[操作和函数类型](xref:microsoft.quantum.language.type-model#operation-and-function-types)。

## <a name="gate"></a>门

基于经典逻辑门的概念的量子[运算](xref:microsoft.quantum.glossary#operation)的一个遗留术语。 [量子电路](xref:microsoft.quantum.glossary#quantum-circuit-diagram)是基于经典逻辑电路的类似概念的门（或操作）网络。

## <a name="global-phase"></a>全球阶段

当两个[状态](xref:microsoft.quantum.glossary#quantum-state)与复数$e[i_phi]$的倍数相同时，它们据说在全局阶段之前有所不同。 与局部阶段不同，全球阶段无法通过任何[测量](xref:microsoft.quantum.glossary#measurement)来观察。 有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="hadamard"></a>Hadamard

Hadamard 操作（也称为 Hadamard 门或变换）在单个[qubit](xref:microsoft.quantum.glossary#qubit)上操作，如果 qubit 最初处于 $ket{0}{0}$ 状态，则将其置于 $ket $或 $$${1}的均匀[叠加中](xref:microsoft.quantum.glossary#superposition)。 在 Q# 中，此操作由预定义的[`H`](xref:microsoft.quantum.intrinsic.h)操作应用。

## <a name="immutable"></a>不可变

其值无法更改的变量。 使用`let`关键字创建 Q# 中的不可变变量。 要声明*可以*更改的变量，请使用[可变](xref:microsoft.quantum.glossary#immutable)关键字声明，`set`使用关键字修改值。 

## <a name="measurement"></a>度量

对产生观测结果的[量子位](xref:microsoft.quantum.glossary#qubit)（或一组量子位）的操作，实际上获取经典位。 有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)。

## <a name="mutable"></a>可变

创建其值后可能会更改的变量。 Q# 中的可变变量使用`mutable`关键字声明并使用 关键字`set`进行修改。 使用`let`关键字创建的变量是不[可变的](xref:microsoft.quantum.glossary#immutable)，并且不能更改其值。

## <a name="namespace"></a>命名空间

相关名称集合（即[操作](xref:microsoft.quantum.glossary#operation)、[函数](xref:microsoft.quantum.glossary#function)和[用户定义类型）](xref:microsoft.quantum.glossary#user-defined-type)的标签。 例如，命名空间[Microsoft.Quantum.准备](xref:microsoft.quantum.preparation)标记标准库中定义的所有符号，以帮助准备初始状态。

## <a name="operation"></a>Operation

Q#中量子执行的基本单位。 它大致等效于 C、C++ 或 Python 中的函数，或 C# 或 Java 中的静态方法。 有关详细信息，请参阅[操作和函数类型](xref:microsoft.quantum.language.type-model#operation-and-function-types)。

## <a name="operator-application"></a>操作员应用程序

执行量子运算。 这通常将单一矩阵应用于当前量子状态矢量。

## <a name="oracle"></a>Oracle

在运行时向量子算法提供与数据相关的信息的子例程。 通常，目标是提供与叠加的输入对应的输出[的叠加](xref:microsoft.quantum.glossary#superposition)。 有关详细信息，请参阅[Oracle](xref:microsoft.quantum.libraries.data-structures#oracles)。

## <a name="partial-application"></a>部分应用

在没有所有所需输入的情况下调用[函数](xref:microsoft.quantum.glossary#function)或[操作](xref:microsoft.quantum.glossary#operation)。 这将返回一个新的[可调用，该参数](xref:microsoft.quantum.glossary#callable)只需要在将来的应用程序期间提供缺少的参数（由下划线指示）。 例如，给定函数`MyFunc(x : int, y : int) : int {return x + y;}`，您可以将其部分应用于新函数`let NewFunc = MyFunc(_, 3)`。 然后，可以使用返回值`NewFunc(2)`*5*的缺失参数稍后调用新函数。  有关详细信息，请参阅[部分应用程序](xref:microsoft.quantum.language.expressions#partial-application)。

## <a name="pauli-operators"></a>保利操作员

一组三个 2 x 2 单一矩阵，`X`称为`Y``Z`和量子运算。 标识矩阵$I$也通常包含在集中。  $I = [开始]bmatrix= \\ \\ 1 & 0 0 & 1 [end_bmatrix]$，$X \\ \\ = [开始]bmatrix] 0 & 1 1 & 0 [结束\\\\]bmatrix$，$Y = [开始]bmatrix0 & -i & \\ \\ 0 [结束]bmatrix$，$Z = [开始]bmatrix] 1 & 0 & -1 [结束]\bmatrix_$。   有关详细信息，请参阅[单量子位操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。

## <a name="quantum-circuit-diagram"></a>量子电路图

一种以图形方式表示简单量子程序[的操作](xref:microsoft.quantum.glossary#operation)序列（或[门](xref:microsoft.quantum.glossary#gate)）的方法，例如![采样电路图。](~/media/qpe.png) 有关详细信息，请参阅[量子电路](xref:microsoft.quantum.concepts.circuits)。

## <a name="quantum-libraries"></a>量子库

用于创建 Q# 程序[的操作](xref:microsoft.quantum.glossary#operation)、[函数](xref:microsoft.quantum.glossary#function)和[用户定义类型的](xref:microsoft.quantum.glossary#user-defined-type)集合。 默认情况下安装[标准库](xref:microsoft.quantum.libraries.standard.intro)。 其他可用的图书馆包括[化学图书馆](xref:microsoft.quantum.chemistry.concepts.intro)、[数字图书馆](xref:microsoft.quantum.numerics.intro)和[机器学习库](xref:microsoft.quantum.machine-learning.concepts.intro)。

## <a name="quantum-state"></a>量子状态

分离量子系统的精确状态，从中可以提取[测量](xref:microsoft.quantum.glossary#measurement)概率。 在量子计算中，量子模拟器使用此信息来模拟量子位如何响应操作。 有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="qubit"></a>量子

量子信息的基本单位，类似于经典计算中的一*点*。 有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="repeat-until-success"></a>重复到成功

概率成功的量子算法。 失败后，例程将重试，直到成功（或已达到限制）。 有关详细信息，请参阅[重复直到成功 （RUS）](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>标准库

[在](xref:microsoft.quantum.glossary#operation)安装过程中与 Q# 编译器一起安装的操作、[函数](xref:microsoft.quantum.glossary#function)和[用户定义类型](xref:microsoft.quantum.glossary#user-defined-type)。 标准库实现与目标计算机无关。 有关详细信息，请参阅[标准库](xref:microsoft.quantum.libraries.standard.intro)。

## <a name="superposition"></a>叠加

量子计算中的概念是[量子位](xref:microsoft.quantum.glossary#qubit)是两种状态的线性组合，$ket_$和 ${1}$$$$$$，直到[被测量](xref:microsoft.quantum.glossary#measurement)为止。  有关详细信息，请参阅[什么是量子计算](xref:microsoft.quantum.overview.what)。

## <a name="target-machine"></a>目标机器

将抽象量子程序降低到硬件或仿真的编译目标。 这通常包括为多种目的重新写入，包括门更换、用于纠错的编码、几何布局等。 有关详细信息，请参阅[量子模拟器和主机应用程序](xref:microsoft.quantum.machines)。

## <a name="teleportation"></a>隐形传送

一种使用[纠缠](xref:microsoft.quantum.glossary#entanglement)和[测量](xref:microsoft.quantum.glossary#measurement)将一个[量子位](xref:microsoft.quantum.glossary#qubit)从一个地方再生数据或[量子态](xref:microsoft.quantum.glossary#quantum-state)的方法，而不实际移动量子位。  有关详细信息，请参阅[量子电路](xref:microsoft.quantum.concepts.circuits)并将其[全部放在一起](xref:microsoft.quantum.techniques.puttingittogether)。

## <a name="tuple"></a>Tuple

充当单个值的逗号分隔值的集合。 元组*的类型*由它包含的值类型定义。 在 Q# 中，tups 是[不可改变的](xref:microsoft.quantum.glossary#immutable)，可以嵌套、包含数组或在数组中使用。 有关详细信息，请参阅[元数类型](xref:microsoft.quantum.language.type-model#tuple-types)。

## <a name="unitary-operator"></a>单一运算符

逆与[等于其邻接](xref:microsoft.quantum.glossary#adjoint)的运算符，即$UU[刀] = \id$。

## <a name="user-defined-type"></a>用户定义类型

可称为单个单元的内置或以前定义的类型的集合。 有关详细信息，请参阅[用户定义的类型](xref:microsoft.quantum.language.type-model#user-defined-types)。