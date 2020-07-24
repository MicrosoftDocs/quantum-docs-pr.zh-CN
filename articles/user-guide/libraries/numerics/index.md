---
title: 量子数字库简介 | Microsoft Docs
description: 量子数字库简介
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: 9552f3683e1df8cb10d19d0b3f85223df056f83d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871342"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>量子数字库简介

许多量子算法依赖于 [oracle](xref:microsoft.quantum.concepts.oracles)，可通过叠加输入来计算数学函数。
例如，秀尔算法的主成分使用固定的 $a$，赋予数值的因子 $N$，以及 $x$ 一个在所有 $2n$ 位字符串上一致叠加的 $2n$ 量子位整数，求 $f(x) = a^x\operatorname{mod} N$ 的值。

若要在实际量子计算机上运行秀尔算法，则必须根据目标计算机的本机操作编写此函数。
使用 $x$ 的二进制表示形式，其中 $x_i$ 表示从最低有效位开始计数的第 $i$ 位，$f(x)$ 可以写为 $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$。
反过来，这可以写为 $a^{2^i x_i}=(a^{2^i})^{x_i}$ 术语的产品 (mod N)。 因此，函数 $f(x)$ 可以使用 $2n$（模）乘序列来实现，其中 $a^{2^i}$ 为条件，$x_i$ 为非零值。 在运行该算法之前，常量 $a^{2^i}$ 可以预计算并规约取模 N。

可以进一步简化此受控模乘的序列：可以使用 $n$ 受控模加的序列来执行每个乘法；每个模加都可以通过常规加法器和比较器构建。


考虑到要得到一个实际的实现需要执行许多步骤，因此从一开始就可以使用这样的功能将非常有帮助。
这就是量子开发工具包支持广泛的数字功能支持的原因。


## <a name="functionality"></a>功能

除了到目前为止提到的整数运算，数字库还提供

- 使用一个或两个量子整数作为输入的有/无符号整数功能（乘法、平方、带余除法、反演...）
- 使用一个或两个量子定点数作为输入的定点功能（加法/减法、乘法、平方、1/x、多项式求值）

## <a name="getting-started"></a>入门

> [!div class="nextstepaction"]
> [了解如何使用数字库](xref:microsoft.quantum.numerics.usage)
