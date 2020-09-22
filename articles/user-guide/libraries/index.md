---
title: Quantum 开发工具包库
description: 概述 Microsoft Quantum 开发工具包中包含的标准库、化学库和数值库。
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 90672b6ec78bf8305bdb3ab8326002cf8ce34bfe
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835717"
---
# <a name="overview-of-no-locq-libraries"></a>Q# 库概述
量子开发工具包附带几个库，让你可以更轻松地以 Q# 中开发量子应用程序。
在文档的此部分中，我们介绍了这些库，以及如何在程序中使用这些库。

- [**标准库**](xref:microsoft.quantum.libraries.standard.intro)：此部分介绍 prelude 和 canon。prelude 定义 Q# 程序与目标计算机之间的接口，canon 是一个 Q# 库，提供用于编写 Q# 程序的常规操作和函数。
- [**量子化学库**](xref:microsoft.quantum.chemistry.concepts.intro)：本部分介绍量子化学库，该库提供了一个数据模型，用于加载 Hamiltonians 费米子的表示形式和用于处理这些表示形式的量子模拟操作和函数。
- [**量子数字库**](xref:microsoft.quantum.numerics.intro)：本部分介绍量子数字库，该库可以实现众多数学函数。 它支持整数（有符号和无符号）和定点表示形式。
- [**量子计算机学习库**](xref:microsoft.quantum.machine-learning.concepts.intro)：本部分介绍量子计算机学习库，该库提供顺序分类器的实现，这些分类器可利用量子计算来了解数据。

从 GitHub 可以获取库和代码示例的原始资料。
有关详细信息，请参阅[许可](xref:microsoft.quantum.libraries.licensing)。 请注意，包引用（“二进制文件”）也适用于库，提供了在项目中包括库的另一种方法。
可以通过 [NuGet](https://nuget.org) 方便地获取它们。
