---
title: 电子系统的量程模式 |Microsoft Docs
description: 电子系统概念文档的量程模型
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 45d134333c8a3c8937d206cb0a4a9cc6101a85df
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184145"
---
# <a name="quantum-models-for-electronic-systems"></a>适用于电子系统的量程模型

为了模拟电子系统，我们需要首先指定 Hamiltonian，这可通过上述规范量化过程来找到。
具体而言，对于 $N _e $ 电子 with momenta $p _i $ （在三个维度中）和大容量 $m _e $ 和位置向量 $x _i $ 和 nuclei，_k $ _k e $ at 位置 $Z Hamiltonian $，\Begin{equation} operator 读取 \hat{H} \Sum = $y {i = 1} ^ {N\__t_1_ e} \frac{\hat{p}\_i ^ 2} {2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_i-\hat{x}\_j |}-\sum\_，k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |}+ \frac{1}{2} \sum_{k\ne k '} \frac{Z\_kZ\_{k '} e ^ 2} {| y\_k ' |}。 \label{eq： Ham} \end{equation} momenta 运算符 $ \hat{p}\_i ^ 2 $ 可以作为 Laplacian 运算符在实际空间中查看，即 $ \hat{p}\_i ^ 2 =-\partial\_{x\_i} ^ 2-\partial\_{y\_i} ^ 2-\partial\_{z\_i} ^ 2 $。
在这里，我们已简化了分子的 nuclei。
这称为 "Oppenheimer" 近似值，它往往适用于 $ \hat{H} $ 的低能耗能量，因为 electron 质量约为 $ 1/1836 $ proton 的质量。
可以通过 $N\_e $ 电子的系统的能耗 e $ 和应用[量程](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)中所述的规范量化过程，轻松找到此 Hamiltonian 运算符。

为了构造 $e ^ {-i\hat {H} t} $ 的单一矩阵表示形式，我们需要将运算符 $ \hat{H} $ 表示为矩阵。
为此，我们需要选择一个坐标系统或基础来表示中的问题。
例如，如果 $ \psi_j $ 是 $N _e $ 电子的一组正交基数函数，则可以定义矩阵

\begin{equation} H\_{i，j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \infty \psi ^ {\*}\_i （x\_1） \hat{H} \psi\_j （x\_2） \dd ^ 3\_1 \dd ^ 3\_2. \ 标签 {eq： discreteHam} \end{equation}

尽管在原则上，运算符 $ \hat{H} $ 是未绑定的，且不会作用于有限的维度空间，但带有元素的矩阵 $H\_\{i，j\}$ 以上。
这意味着，如果在基本设置中选取太小，则会产生错误;但是，选取一种较大的基础可以模拟化学 dynamics 不切实际。
出于此原因，选择可简明地表示问题的基数对于解决电子结构问题至关重要。

可以使用许多合适的基准，并选择适当的基础来适应问题，这是量程化学的一大优点。
最简单的这种基本设置可能是 Slater Orbitals （停止），这是针对类似于 Schrödinger 的原子的 Eigenfunctions 公式（即，\hat{H} $ hydrogen $）的（orthogonalized）解决方案。
可以使用其他基础集（如平面-波浪或实空格 orbitals），更详细地说，我们将好奇的读者称为标准文本["分子电子结构理论"](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572)的 Helgaker。

虽然以上模型中使用的状态看起来可能是任意的，但量程机制对可在本质上发现的状态施加限制。
特别是，在 electron 标签的交换下，所有有效的电子量程状态都必须是反对称状态。
也就是说，如果 $ \psi （x_1，x_2） $ 是两个电子的联合量程状态的波形函数，则必须具有 $ $ \psi （x_1，x_2） =-\psi （x_2，x_1）。
$ $ Pauli 排除原则，它禁止两个电子处于相同的量程状态，fascinatingly，这一法律的直接后果是，这是因为我们交换了两个位于同一位置 $ 电子（\psi，x_1） x_1 \mapsto 的 \psi （x_1，x_1） \ne-\psi （x_1，x_1） $，除非 $ \psi （x_1，x_1） = 0 $。
因此，必须将初始状态选为遵循这种抗对称属性，而不会同时使两个电子处于相同状态。
这对电子结构至关重要，因为它禁止多个电子处于相同的状态，进而允许量子计算机使用单个量程位来存储给定量程状态下的电子数。

尽管量程机制可以通过离散化这些状态在量程计算机上模拟，但该字段中的大部分工作都 eschewed 这种方法，因为它需要许多 qubits 来存储状态，并需要一个复杂的状态准备过程来准备反对称初始状态。
幸运的是，这些问题可以通过从不同的角度查看模拟问题来 sidestepped。
