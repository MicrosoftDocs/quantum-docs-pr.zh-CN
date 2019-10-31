---
title: Q# 标准库 - 简介 | Microsoft Docs
description: Q# 标准库 - 简介
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 547f4f6066e3ead627cd2a5970b1555999e988bb
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056385"
---
# <a name="introduction-to-the-q-standard-libraries"></a><span data-ttu-id="e21c9-103">Q# 标准库简介</span><span class="sxs-lookup"><span data-stu-id="e21c9-103">Introduction to the Q# Standard Libraries</span></span> #

<span data-ttu-id="e21c9-104">Q# 由包含 Q # 标准库的各种不同的有用操作、函数和用户定义的类型支持  。</span><span class="sxs-lookup"><span data-stu-id="e21c9-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="e21c9-105">[安装和验证](xref:microsoft.quantum.install)过程中安装的 [`Microsoft.Quantum.Development.Kit` NuGet 包](https://www.nuget.org/packages/microsoft.quantum.development.kit) 提供了 Q# 编译器，以及由目标计算机实现的标准库的一部分。</span><span class="sxs-lookup"><span data-stu-id="e21c9-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="e21c9-106">[`Microsoft.Quantum.Standard` 包](https://www.nuget.org/packages/microsoft.quantum.standard) 提供了可在目标计算机之间移植的 Q# 标准库的一部分。</span><span class="sxs-lookup"><span data-stu-id="e21c9-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="e21c9-107">由 Q# 标准库定义的符号在 [API 文档](xref:microsoft.quantum.standardlibsintro)中更详尽地定义。</span><span class="sxs-lookup"><span data-stu-id="e21c9-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="e21c9-108">在以下部分中，我们将概述标准库的每个部分的最重要功能，并提供有关如何在实践中使用每个功能的一些上下文。</span><span class="sxs-lookup"><span data-stu-id="e21c9-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
