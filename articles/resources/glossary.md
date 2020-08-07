---
标题：量程计算词汇表说明：标准术语、操作和量程计算中使用的对象的词汇表。
author： QuantumWriter： Alan.Geller@microsoft.com ms. 日期： 12/11/2017 ms. 主题：文章 uid： microsoft 量子：
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="quantum-computing-glossary"></a>量程计算术语表

## <a name="adjoint"></a>Adjoint

[操作](xref:microsoft.quantum.glossary#operation)的复杂共轭转置。 对于实现[单一](xref:microsoft.quantum.glossary#unitary-operator)运算符的操作，adjoint 是操作的反向，由剑号符号指示。 例如，如果操作 `U` 表示单一运算符 $ U $ ，则 `Adjoint U` 表示 $ u ^ \dagger $ 。 有关详细信息，请参阅[Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。

## <a name="ancilla"></a>Ancilla

一个[qubit](xref:microsoft.quantum.glossary#qubit) ，它充当量子计算机的临时内存，并根据需要分配和取消分配。  有关详细信息，请参阅[多个 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。

## <a name="bell-state"></a>电铃状态

四个特定最大化[放大](xref:microsoft.quantum.glossary#entanglement)[量程](xref:microsoft.quantum.glossary#quantum-state)中的一种状态，分为两 qubits。 定义了四个状态： " $ \ket { \beta { ij } } = (\mathbb { I } \otimes X ^ iZ ^ j)  (\ket { 00 }  +  \ket { 11 }) / \sqrt { 2 } $ 。 电铃状态也称为[EPR 对](xref:microsoft.quantum.glossary#epr-pair)。

## <a name="bloch-sphere"></a>Bloch 球体

[Qubit](xref:microsoft.quantum.glossary#qubit) [量程状态](xref:microsoft.quantum.glossary#quantum-state)的图形表示形式，作为三维单位球体中的点。 有关详细信息，请参阅[使用 Bloch 球体直观显示 Qubits 和转换](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)。

## <a name="callable"></a>多次

语言中的[操作](xref:microsoft.quantum.glossary#operation)或[函数](xref:microsoft.quantum.glossary#function) Q# 。 有关详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="clifford-group"></a>Clifford 组

一组操作，这些操作占用[Bloch 球](xref:microsoft.quantum.glossary#bloch-sphere)的 octants 并影响[Pauli 运算符](xref:microsoft.quantum.glossary#pauli-operators)的效果。 其中包括操作[ $ X $ ](xref:microsoft.quantum.intrinsic.x)、 [ $ Y $ ](xref:microsoft.quantum.intrinsic.y)、 [ $ Z $ ](xref:microsoft.quantum.intrinsic.z)、 [ $ H $ ](xref:microsoft.quantum.intrinsic.h)和[ $ S $ ](xref:microsoft.quantum.intrinsic.s)。

## <a name="controlled"></a>操控

一个量程[操作](xref:microsoft.quantum.glossary#operation)，它将一个或多个[qubits](xref:microsoft.quantum.glossary#qubit)作为目标操作的启用程序。 有关详细信息，请参阅[受控和 adjoint 操作](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。

## <a name="dirac-notation"></a>Dirac 表示法

简化[量程状态](xref:microsoft.quantum.glossary#quantum-state)表示形式的符号简写，也称为*寄存器-票证*表示法。  *寄存器*部分表示一个行向量，例如 a $ \bra { } = \begin{bmatrix} { _1 } & a { _2 } \end{bmatrix} $ ，而*票证*部分表示一个列向量， $ \ket { b } = \begin{bmatrix} b { _1 } \\\\ b { _2 } \end{bmatrix} $ 。 有关详细信息，请参阅[Dirac 表示法](xref:microsoft.quantum.concepts.dirac)。

## <a name="eigenvalue"></a>Eigenvalue

转换应用程序更改给定转换的[eigenvector](xref:microsoft.quantum.glossary#eigenvector)的量的因子。  给定正方形 matrix $ M $ 和 eigenvector $ v $ ，然后使用 $ Mv = cv $ ，其中 $ c $ 是 eigenvalue，可以是任意参数的复数。 有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="eigenvector"></a>Eigenvector

一个向量，其方向与给定的转换保持不变，并且其量的值由与该向量的[eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)相对应的系数更改。 给定正方形 matrix $ M $ 和 eigenvalue $ c $ ，then $ Mv = cv $ ，其中 $ v $ 是矩阵的 eigenvector，可以是任意参数的复数。 有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="entanglement"></a>纠缠

量程粒子（如[qubits](xref:microsoft.quantum.glossary#qubit)）可以连接或*放大*，以使它们不能彼此独立地进行描述。 即使它们被无限远地分离，它们的度量结果也是相关的。 牵连对于[测量](xref:microsoft.quantum.glossary#measurement)qubit 的[状态](xref:microsoft.quantum.glossary#quantum-state)至关重要。  有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="epr-pair"></a>EPR 对

四个特定最大化放大量程中的一种[状态](xref:microsoft.quantum.glossary#quantum-state)，分为两[qubits](xref:microsoft.quantum.glossary#qubit)。 四种状态定义为： $ \ket { \beta { } } = (\mathbb { 1 } \otimes X ^ iZ ^ j)  (\ket { 00 }  +  \ket { 11 }) / \sqrt { 2 } $ 。 EPR 对也称为[钟形状态](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>演变

[量程状态](xref:microsoft.quantum.glossary#quantum-state)随时间变化的方式。 有关详细信息，请参阅[Matrix 指数](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)。

## <a name="function"></a>函数
一种 Q# 纯传统 (非量程) 的一种子例程。 当函数在量程算法中使用时，它们不能作用于[qubits](xref:microsoft.quantum.glossary#qubit)或调用[操作](xref:microsoft.quantum.glossary#operation)。 有关详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="gate"></a>护

基于传统逻辑入口的概念的量程[操作](xref:microsoft.quantum.glossary#operation)的旧术语。 [量程线路](xref:microsoft.quantum.glossary#quantum-circuit-diagram)是基于传统逻辑电路的类似概念的 (或操作) 的入口网络。

## <a name="global-phase"></a>全局阶段

当两个[状态](xref:microsoft.quantum.glossary#quantum-state)的最大值为 e ^ i 的复数的倍数时 $ { \phi } $ ，它们被认为是不同于全局阶段的。 与本地阶段不同，全局阶段不能通过任何[measurment](xref:microsoft.quantum.glossary#measurement)来观察。 有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="hadamard"></a>Hadamard

Hadamard 操作 (也称为 Hadamard 入口或变换) 作用于单个[qubit](xref:microsoft.quantum.glossary#qubit) ，并将其置于[superposition](xref:microsoft.quantum.glossary#superposition) $ \ket { 0 或1之间， } $ $ \ket { } $ 如果 qubit 最初处于 $ \ket { 0 } $ 状态。 在中 Q# ，此操作由预定义的操作应用 [`H`](xref:microsoft.quantum.intrinsic.h) 。

## <a name="immutable"></a>不可变

不能更改其值的变量。 使用关键字创建中的不可变变量 Q# `let` 。 若要声明*可*更改的变量，请使用[可变](xref:microsoft.quantum.glossary#immutable)关键字进行声明，使用 `set` 关键字修改该值。 

## <a name="measurement"></a>度量

[Qubit](xref:microsoft.quantum.glossary#qubit) (或一组 qubits) 的操作，该操作生成观察结果，实际上获取的是传统位。 有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)。

## <a name="mutable"></a>可变

其值在创建后可以更改的变量。 中的可变变量 Q# 使用关键字进行声明 `mutable` ，并使用关键字进行修改 `set` 。 用关键字创建的变量 `let` 是[不可变](xref:microsoft.quantum.glossary#immutable)的，不能更改其值。

## <a name="namespace"></a>命名空间

相关名称集合的标签 (例如，[操作](xref:microsoft.quantum.glossary#operation)、[函数](xref:microsoft.quantum.glossary#function)和[用户定义的类型](xref:microsoft.quantum.glossary#user-defined-type)) 。 例如，命名空间为 ""。[准备](xref:microsoft.quantum.preparation)标签在标准库中定义的所有符号都有助于准备初始状态。

## <a name="operation"></a>操作

中量程执行的基本单位 Q# 。 它大致等效于 C、c + + 或 Python 中的函数或 c # 或 Java 中的静态方法。 有关详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="operator-application"></a>操作员应用程序

执行量程运算。 这通常会将单一矩阵应用于当前的量程状态向量。

## <a name="oracle"></a>Oracle

在运行时提供量程算法的数据相关信息的子例程。 通常，目标是提供与 superposition 中的输入对应的输出[superposition](xref:microsoft.quantum.glossary#superposition) 。 有关详细信息，请参阅[Oracles](xref:microsoft.quantum.libraries.data-structures#oracles)。

## <a name="partial-application"></a>部分应用程序

调用不包含所有必需输入的[函数](xref:microsoft.quantum.glossary#function)或[操作](xref:microsoft.quantum.glossary#operation)。 这会返回一个新的可调用，该[调用](xref:microsoft.quantum.glossary#callable)只需在以后的应用程序中提供的下划线)  (所需的缺少参数。 例如，假设函数 `MyFunc(x : int, y : int) : int {return x + y;}` 可部分应用于新函数 `let NewFunc = MyFunc(_, 3)` 。 然后，你可以在以后使用缺少的参数 `NewFunc(2)` （返回值*5*）调用新函数。  有关详细信息，请参阅[部分应用程序](xref:microsoft.quantum.guide.operationsfunctions#partial-application)。

## <a name="pauli-operators"></a>Pauli 运算符

由三个 2 x 2 个单一矩阵组成的一组 `X` ，称为 `Y` 和一个 `Z` 量程运算。 恒等矩阵 $ $ 通常也包含在集中。  $I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} $ ， $ X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} $ ， $ Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix} $ ， $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} $ 。   有关详细信息，请参阅[qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。

## <a name="quantum-circuit-diagram"></a>量程线路关系图

用于以图形方式表示简单量程程序的[操作](xref:microsoft.quantum.glossary#operation)序列 (或[入口](xref:microsoft.quantum.glossary#gate)) 的方法，例如 

![示例线路图示](~/media/qpe.png). 

有关详细信息，请参阅[量子线路](xref:microsoft.quantum.concepts.circuits)。

## <a name="quantum-libraries"></a>量程库

用于创建程序的[操作](xref:microsoft.quantum.glossary#operation)、[函数](xref:microsoft.quantum.glossary#function)和[用户定义类型](xref:microsoft.quantum.glossary#user-defined-type)的集合 Q# 。 默认情况下，将安装[标准库](xref:microsoft.quantum.libraries.standard.intro)。 可用的其他库包括[化学库](xref:microsoft.quantum.chemistry.concepts.intro)、数字[库](xref:microsoft.quantum.numerics.intro)和[机器学习库](xref:microsoft.quantum.machine-learning.concepts.intro)。

## <a name="quantum-state"></a>量程状态

隔离的量程系统的准确状态，可以从中提取[度量](xref:microsoft.quantum.glossary#measurement)概率。 在量程计算中，量程模拟器使用此信息来模拟 qubits 响应操作的方式。 有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="qubit"></a>Qubit

量程信息的基本单位，类似于传统计算中的*位*。 有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="repeat-until-success"></a>重复执行-成功

Probabilistic 成功的量程算法。 如果失败，例程将重试，直到成功 (或已达到限制) 。 有关详细信息，请参阅[重复到成功 (ru) ](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>标准库

安装期间随编译器一起安装的[操作](xref:microsoft.quantum.glossary#operation)、[函数](xref:microsoft.quantum.glossary#function)和[用户定义类型](xref:microsoft.quantum.glossary#user-defined-type) Q# 。 标准库实现对于目标计算机而言不可知。 有关详细信息，请参阅[标准库](xref:microsoft.quantum.libraries.standard.intro)。

## <a name="superposition"></a>Superposition

量程计算中的概念计算， [qubit](xref:microsoft.quantum.glossary#qubit)是两个状态（ $ \ket { 0 } $ 和1）的线性组合 $ \ket { } $ ，直到[测量](xref:microsoft.quantum.glossary#measurement)为止。  有关详细信息，请参阅[了解量程计算](xref:microsoft.quantum.overview.understanding)。

## <a name="target-machine"></a>目标计算机

一种编译目标，它将抽象的量程程序降低到硬件或模拟。 这通常包括重新编写以实现多种目的，包括门替换、用于纠错的编码、几何布局和其他功能。 有关详细信息，请参阅[量程模拟器和主机应用程序](xref:microsoft.quantum.machines)。

## <a name="teleportation"></a>隐形传送

一种方法，用于将一个[qubit](xref:microsoft.quantum.glossary#qubit)的数据（即[量程状态](xref:microsoft.quantum.glossary#quantum-state)）从一个位置重新生成到另一个位置，而无需使用[牵连](xref:microsoft.quantum.glossary#entanglement)和[度量](xref:microsoft.quantum.glossary#measurement)实际移动 qubit。  有关详细信息，请参阅[量子线路](xref:microsoft.quantum.concepts.circuits)和[量子 Katas](xref:microsoft.quantum.overview.katas)的相应 kata。

## <a name="tuple"></a>Tuple

作为单个值的逗号分隔值的集合。 元组的*类型*由其包含的值的类型定义。 在中 Q# ，元组是[不可变](xref:microsoft.quantum.glossary#immutable)的，并且可以嵌套、包含数组或用于数组。 有关详细信息，请参阅[元组类型](xref:microsoft.quantum.guide.types#tuple-types)。

## <a name="unitary-operator"></a>单一运算符

一个运算符，其反正等于其[adjoint](xref:microsoft.quantum.glossary#adjoint)，即， $ UU ^ { \dagger } = \id $ 。

## <a name="user-defined-type"></a>用户定义类型

可能称为单个单元的内置或以前定义的类型的集合。 有关详细信息，请参阅[用户定义类型](xref:microsoft.quantum.guide.types#user-defined-types)。