---
title: Microsoft Q# 标准库简介
description: 了解用于定义量子程序中使用的操作、函数和数据类型的 Microsoft Q# 标准库。
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868468"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Q# 标准库简介

Q# 由包含 Q# 标准库的各种不同的有用操作、函数和用户定义的类型支持。
[安装和验证](xref:microsoft.quantum.install)过程中安装的 [`Microsoft.Quantum.Development.Kit` NuGet 包](https://www.nuget.org/packages/microsoft.quantum.development.kit) 提供了 Q# 编译器，以及由目标计算机实现的标准库的一部分。
[`Microsoft.Quantum.Standard` 包](https://www.nuget.org/packages/microsoft.quantum.standard) 提供了可在目标计算机之间移植的 Q# 标准库的一部分。

由 Q# 标准库定义的符号在 [API 文档](xref:microsoft.quantum.standardlibsintro)中更详尽地定义。

在以下部分中，我们将概述标准库的每个部分的最重要功能，并提供有关如何在实践中使用每个功能的一些上下文。
