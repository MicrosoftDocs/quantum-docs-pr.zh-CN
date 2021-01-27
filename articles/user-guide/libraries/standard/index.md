---
title: Microsoft Q# 标准库简介
description: 了解用于定义量子程序中使用的操作、函数和数据类型的 Microsoft Q# 标准库。
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 58e271fefba84e45c5558eeee066bc37c22bf63b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858320"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="08972-103">Q# 标准库简介</span><span class="sxs-lookup"><span data-stu-id="08972-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="08972-104">Q# 由包含 Q# 标准库的各种不同的有用操作、函数和用户定义的类型支持。</span><span class="sxs-lookup"><span data-stu-id="08972-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="08972-105">[安装和验证](xref:microsoft.quantum.install)过程中安装的 [`Microsoft.Quantum.Development.Kit` NuGet 包](https://www.nuget.org/packages/microsoft.quantum.development.kit) 提供了 Q# 编译器，以及由目标计算机实现的标准库的一部分。</span><span class="sxs-lookup"><span data-stu-id="08972-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="08972-106">[`Microsoft.Quantum.Standard` 包](https://www.nuget.org/packages/microsoft.quantum.standard) 提供了可在目标计算机之间移植的 Q# 标准库的一部分。</span><span class="sxs-lookup"><span data-stu-id="08972-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="08972-107">由 Q# 标准库定义的符号在 [API 文档](xref:microsoft.quantum.apiref-intro)中更详尽地定义。</span><span class="sxs-lookup"><span data-stu-id="08972-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.apiref-intro).</span></span>

<span data-ttu-id="08972-108">在以下部分中，我们将概述标准库的每个部分的最重要功能，并提供有关如何在实践中使用每个功能的一些上下文。</span><span class="sxs-lookup"><span data-stu-id="08972-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
