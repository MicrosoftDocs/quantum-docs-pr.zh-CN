---
title: 适用于电子系统的量程模型
description: 了解如何使用量程建模来模拟分子电子系统。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
no-loc:
- Q#
- $$v
ms.openlocfilehash: f6b652ef3e315ded5b4e39fd65a2f6be7070d7fa
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869471"
---
# <a name="quantum-models-for-electronic-systems"></a>适用于电子系统的量程模型

为了模拟电子系统，我们需要首先指定 Hamiltonian，这可通过上述规范量化过程来找到。
具体而言，对于 $N _e $ 电子 with momenta $p _i 在三个维度中的 $ () $m $ 和位置矢量 _e $x $ 和 nuclei，同时 _i $Z $，Hamiltonian 运算符读取 \begin{equation} \hat{H} = \sum \_ {i = 1} ^ {N \_ e} \frac{\hat{p} \_ i ^ 2} {2m \_ e} + \frac {1} {2} \sum \_ {i\ne j} \frac{e ^ 2} {| \hat{x} \hat{x} \_ \_ j |}-\sum \_ {i，k} \frac{Z \_ ke ^ 2} {| \hat{x} \_ i-{y} \_ k |}+ \frac {1} {2} \ sum_ {k\ne k '} \frac{Z \_ kZ \_ {k '} e ^ 2} {| y \_ k y \_ k ' |}。 \label{eq： Ham} \end{equation} momenta 运算符 $ \hat{p} \_ i ^ 2 $ 可以在实际空间中查看为 Laplacian 运算符，即 $ \hat{p} \_ i ^ 2 =-\partial \_ {x \_ i} ^ 2-\partial { \_ y i} \_ ^ 2-\partial \_ {z \_ i} ^ 2 $。
在这里，我们已简化了分子的 nuclei。
这称为 "Oppenheimer" 近似值，它往往适用于 $ \hat{H} $ 的低能耗能量，因为 electron 质量约为 $ 1/1836 $ proton 的质量。
可以通过为 $N e $ 电子的系统写出能量 \_ ，并应用[量程动态](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)中所述的规范量化过程，轻松找到此 Hamiltonian 运算符。

为了构造 $e ^ {-i\hat {H} t} $ 的单一矩阵表示形式，我们需要将运算符 $ \hat{H} $ 表示为矩阵。
为此，我们需要选择一个坐标系统或基础来表示中的问题。
例如，如果 $ \ psi_j $ 是 $N 的一组正交的基础函数 _e $ 电子，则可以定义矩阵

\begin{equation} H \_ {i，j} = \int \_ {-\infty} ^ \infty\int \_ {-\infty} ^ \infty \psi ^ { \* } \_ i (x \_ 1) \hat{H} \psi \_ j (x \_ 2) \dd ^ 3 x \_ \Dd ^ \_ 2. \ label {eq： discreteHam} \end{equation}

尽管在原则上，运算符 $ \hat{H} $ 是不受限制的，并且不会作用于有限的维度空间，但上面带有元素的矩阵 $H \_ \{ i，j \} $ 以上。
这意味着，如果在基本设置中选取太小，则会产生错误;但是，选取一种较大的基础可以模拟化学 dynamics 不切实际。
出于此原因，选择可简明地表示问题的基数对于解决电子结构问题至关重要。

可以使用许多合适的基准，并选择适当的基础来适应问题，这是量程化学的一大优点。
最简单的这种基本设置可能是 Slater Orbitals (停止) ， (orthogonalized) 到 Schrödinger 的 eigenfunctions 的解决方案 (例如，\hat{H} 的。
可以使用其他基础集（如平面-波浪或实空格 orbitals），更详细地说，我们将好奇的读者称为标准文本["分子电子结构理论"](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572)的 Helgaker。

虽然以上模型中使用的状态看起来可能是任意的，但量程机制对可在本质上发现的状态施加限制。
特别是，在 electron 标签的交换下，所有有效的电子量程状态都必须是反对称状态。
也就是说，如果 $ \psi (x_1，x_2) $ 是两个电子的联合量程状态的波形函数，则必须让 $ $ \psi (x_1 x_2) =-\psi (x_2 x_1) 。
$ $ Pauli 排除原则，此原则会禁止两个电子处于相同的量程状态，fascinatingly，这一法律的直接后果就是 intuited，因为我们将两个电子 x_1 的位置、x_1) \mapsto \psi (x_1 x_1)  ($，除非 $ \ne x_1 x_1 ()  (x_1 x_1) 。 $0
因此，必须将初始状态选为遵循这种抗对称属性，而不会同时使两个电子处于相同状态。
这对电子结构至关重要，因为它禁止多个电子处于相同的状态，进而允许量子计算机使用单个量程位来存储给定量程状态下的电子数。

尽管量程机制可以通过离散化这些状态在量程计算机上模拟，但该字段中的大部分工作都 eschewed 了这种方法，因为它需要许多 qubits 来存储状态，并需要使用复杂的状态准备过程来准备反对称的初始状态。
幸运的是，这些问题可以通过从不同的角度查看模拟问题来 sidestepped。
