---
title: Quantum 开发工具包库
description: 概述 Microsoft Quantum 开发工具包中包含的标准库、化学库和数值库。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 89612aaa5c11e1a5e0d418256e96366953fdd3fe
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906400"
---
# <a name="overview-of-q-libraries"></a>Q# 库概述
量子开发工具包附带几个库，让在 Q# 中开发量子应用程序变得更轻松。
在文档的此部分中，我们介绍了这些库，以及如何在程序中使用这些库。

- [**标准库**](xref:microsoft.quantum.libraries.standard.intro)：此部分介绍 prelude 和 canon。prelude 定义 Q# 程序与目标计算机之间的接口，canon 是一个 Q# 库，提供用于编写 Q# 程序的常规操作和函数。
- [**量子化学库**](xref:microsoft.quantum.chemistry.concepts.intro)：本部分介绍量子化学库，该库提供了一个数据模型，用于加载 Hamiltonians 费米子的表示形式和用于处理这些表示形式的量子模拟操作和函数。
- [**量子数字库**](xref:microsoft.quantum.numerics.intro)：本部分介绍量子数字库，该库可以实现众多数学函数。 它支持整数（有符号和无符号）和定点表示形式。

从 GitHub 可以获取库和代码示例的原始资料。 有关详细信息，另请参阅[许可](xref:microsoft.quantum.libraries.licensing)部分。 请注意，包引用（“二进制”）也适用于库，因此提供了在项目中添加库的另一种方法。 通过使用 [nuget](https://nuget.org) 可以方便地获取这些资源。
