---
title: 量子开发工具包预览版发行说明
description: 量子开发工具包预览版发行说明
author: natke
ms.author: nakersha
ms.date: 09/30/2019
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: 169a8ac31c53f2892624618a227d8bdbdc458458
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "72958873"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a><span data-ttu-id="041b1-103">Microsoft 量子开发工具包发行说明</span><span class="sxs-lookup"><span data-stu-id="041b1-103">Microsoft Quantum Development Kit Release Notes</span></span>

<span data-ttu-id="041b1-104">本文包含有关每个量子开发工具包版本的信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-104">This article contains information on each Quantum Development Kit release.</span></span>

<span data-ttu-id="041b1-105">有关安装说明，请参阅[安装指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="041b1-105">For installation instructions, please refer to the [install guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="041b1-106">有关更新说明，请参阅[更新指南](xref:microsoft.quantum.update)。</span><span class="sxs-lookup"><span data-stu-id="041b1-106">For update instructions, please refer to the [update guide](xref:microsoft.quantum.update).</span></span>

## <a name="version-0919093002"></a><span data-ttu-id="041b1-107">版本 0.9.1909.3002</span><span class="sxs-lookup"><span data-stu-id="041b1-107">Version 0.9.1909.3002</span></span>

<span data-ttu-id="041b1-108">发行日期：  2019 年 9 月 30 日</span><span class="sxs-lookup"><span data-stu-id="041b1-108">*Release date: September 30th, 2019*</span></span>

<span data-ttu-id="041b1-109">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="041b1-109">This release contains the following:</span></span>

- <span data-ttu-id="041b1-110">对 Visual Studio 2019（16.3 版本和更高版本）和 Visual Studio Code 中的 Q# 代码补全的新支持</span><span class="sxs-lookup"><span data-stu-id="041b1-110">New support for Q# code completion in Visual Studio 2019 (versions 16.3 & later) & Visual Studio Code</span></span>
- <span data-ttu-id="041b1-111">量子添加器的新[量子 Kata](https://github.com/Microsoft/QuantumKatas)</span><span class="sxs-lookup"><span data-stu-id="041b1-111">New [Quantum Kata](https://github.com/Microsoft/QuantumKatas) for quantum adders</span></span>

<span data-ttu-id="041b1-112">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="041b1-112">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-09-packagereference-0919082902"></a><span data-ttu-id="041b1-113">版本 0.9 (PackageReference 0.9.1908.2902) </span><span class="sxs-lookup"><span data-stu-id="041b1-113">Version 0.9 (*PackageReference 0.9.1908.2902*)</span></span>

<span data-ttu-id="041b1-114">发行日期：  2019 年 8 月 29 日</span><span class="sxs-lookup"><span data-stu-id="041b1-114">*Release date: August 29th, 2019*</span></span>

<span data-ttu-id="041b1-115">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="041b1-115">This release contains the following:</span></span>

- <span data-ttu-id="041b1-116">对 Q# 中 [conjugation 语句](xref:microsoft.quantum.language.statements#conjugations)的新支持</span><span class="sxs-lookup"><span data-stu-id="041b1-116">New support for [conjugation statements](xref:microsoft.quantum.language.statements#conjugations) in Q#</span></span>
- <span data-ttu-id="041b1-117">编译器中新的代码操作，例如：“replace with”、“add documentation”和简单数组项更新</span><span class="sxs-lookup"><span data-stu-id="041b1-117">New code actions in the compiler, such as: "replace with", "add documentation", and simple array item update</span></span>
- <span data-ttu-id="041b1-118">已将安装模板和新项目命令添加到 Visual Studio Code 扩展</span><span class="sxs-lookup"><span data-stu-id="041b1-118">Added install template and new project commands to Visual Studio Code extension</span></span>
- <span data-ttu-id="041b1-119">添加了 ApplyIf 连结符的新变体，例如 [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span><span class="sxs-lookup"><span data-stu-id="041b1-119">Added new variants of ApplyIf combinator such as [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span></span>
- <span data-ttu-id="041b1-120">已转换为 Jupyter Notebook 的其他[量子 Katas](https://github.com/Microsoft/QuantumKatas)</span><span class="sxs-lookup"><span data-stu-id="041b1-120">Additional [Quantum Katas](https://github.com/Microsoft/QuantumKatas) converted to Jupyter Notebooks</span></span>
- <span data-ttu-id="041b1-121">Visual Studio 扩展现在需要 Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="041b1-121">Visual Studio Extension now requires Visual Studio 2019</span></span>

<span data-ttu-id="041b1-122">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="041b1-122">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="041b1-123">此处汇总了这些更改，以及有关升级现有程序的说明。</span><span class="sxs-lookup"><span data-stu-id="041b1-123">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="041b1-124">有关这些更改的详细信息，请参阅 [Q# 开发博客](https://devblogs.microsoft.com/qsharp)。</span><span class="sxs-lookup"><span data-stu-id="041b1-124">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

## <a name="version-08-packagereference-0819071701"></a><span data-ttu-id="041b1-125">版本 0.8 (*PackageReference 0.8.1907.1701*)</span><span class="sxs-lookup"><span data-stu-id="041b1-125">Version 0.8 (*PackageReference 0.8.1907.1701*)</span></span>

<span data-ttu-id="041b1-126">发行日期：  2019 年 7 月 12 日</span><span class="sxs-lookup"><span data-stu-id="041b1-126">*Release date: July 12, 2019*</span></span>

<span data-ttu-id="041b1-127">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="041b1-127">This release contains the following:</span></span>

- <span data-ttu-id="041b1-128">用于对数组进行切片的新索引位置，请参阅[语言参考](xref:microsoft.quantum.language.expressions#array-slices)了解详情。</span><span class="sxs-lookup"><span data-stu-id="041b1-128">New indexing locations for slicing arrays, [see the language reference](xref:microsoft.quantum.language.expressions#array-slices) for more information.</span></span>
- <span data-ttu-id="041b1-129">[Microsoft 容器注册表](https://github.com/microsoft/ContainerRegistry)上托管的附加 Dockerfile，请参阅 [IQ# 存储库](https://github.com/microsoft/iqsharp/blob/master/README.md)了解详情</span><span class="sxs-lookup"><span data-stu-id="041b1-129">Added Dockerfile hosted on the [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry), see the [IQ# repository for more information](https://github.com/microsoft/iqsharp/blob/master/README.md)</span></span>
- <span data-ttu-id="041b1-130">[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的中断性变更、配置设置更新、名称更改；请参阅 [.NET API 浏览器](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)了解更新后的名称。</span><span class="sxs-lookup"><span data-stu-id="041b1-130">Breaking change for [the trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), update to configuration settings, name changes; see the [.NET API Browser for the updated names](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).</span></span>

<span data-ttu-id="041b1-131">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="041b1-131">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-07-packagereference-0719053109"></a><span data-ttu-id="041b1-132">版本 0.7 (*PackageReference 0.7.1905.3109*)</span><span class="sxs-lookup"><span data-stu-id="041b1-132">Version 0.7 (*PackageReference 0.7.1905.3109*)</span></span>

<span data-ttu-id="041b1-133">发行日期：  2019 年 5 月 31 日</span><span class="sxs-lookup"><span data-stu-id="041b1-133">*Release date: May 31, 2019*</span></span>

<span data-ttu-id="041b1-134">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="041b1-134">This release contains the following:</span></span>
- <span data-ttu-id="041b1-135">Q# 语言的附加内容、</span><span class="sxs-lookup"><span data-stu-id="041b1-135">additions to the Q# language,</span></span> 
- <span data-ttu-id="041b1-136">化学库的更新、</span><span class="sxs-lookup"><span data-stu-id="041b1-136">updates to the chemistry library,</span></span> 
- <span data-ttu-id="041b1-137">新的数字库。</span><span class="sxs-lookup"><span data-stu-id="041b1-137">a new numerics library.</span></span>

<span data-ttu-id="041b1-138">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="041b1-138">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="041b1-139">此处汇总了这些更改，以及有关升级现有程序的说明。</span><span class="sxs-lookup"><span data-stu-id="041b1-139">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="041b1-140">有关这些更改的详细信息，请参阅 [Q# 开发博客](https://devblogs.microsoft.com/qsharp)。</span><span class="sxs-lookup"><span data-stu-id="041b1-140">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

### <a name="q-language-syntax"></a><span data-ttu-id="041b1-141">Q# 语言语法</span><span class="sxs-lookup"><span data-stu-id="041b1-141">Q# language syntax</span></span>
<span data-ttu-id="041b1-142">此版本添加了新的 Q# 语言语法：</span><span class="sxs-lookup"><span data-stu-id="041b1-142">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="041b1-143">添加了[用户定义类型](xref:microsoft.quantum.language.type-model#user-defined-types)的命名项。</span><span class="sxs-lookup"><span data-stu-id="041b1-143">Add named items for [user-defined types](xref:microsoft.quantum.language.type-model#user-defined-types).</span></span>  
* <span data-ttu-id="041b1-144">现可将用户定义类型构造函数用作函数。</span><span class="sxs-lookup"><span data-stu-id="041b1-144">User-defined type constructors can now be used as functions.</span></span>
* <span data-ttu-id="041b1-145">在用户定义类型中添加了对 [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) 和 [apply-and-reassign]((xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)) 的支持。</span><span class="sxs-lookup"><span data-stu-id="041b1-145">Add support for [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) and [apply-and-reassign]((xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)) in user-defined types.</span></span>
* <span data-ttu-id="041b1-146">[repeat-until-success](xref:microsoft.quantum.language.statements#repeat-until-success-loop) 循环的修复块现在是可选项。</span><span class="sxs-lookup"><span data-stu-id="041b1-146">Fixup-block for [repeat-until-success](xref:microsoft.quantum.language.statements#repeat-until-success-loop) loops is now optional.</span></span>
* <span data-ttu-id="041b1-147">我们现支持在函数中（而不是在操作中）使用 while 循环。</span><span class="sxs-lookup"><span data-stu-id="041b1-147">We now support while loops in functions (not in operations).</span></span>

### <a name="library"></a><span data-ttu-id="041b1-148">库</span><span class="sxs-lookup"><span data-stu-id="041b1-148">Library</span></span> 

<span data-ttu-id="041b1-149">此版本添加了数字库：详细了解如何[使用新的数字库](xref:microsoft.quantum.numerics.usage)并尝试[新的示例](https://github.com/microsoft/quantum/tree/master/Numerics)。</span><span class="sxs-lookup"><span data-stu-id="041b1-149">This release adds a numerics library: Learn more about how to [use the new numerics library](xref:microsoft.quantum.numerics.usage) and try out the [new samples](https://github.com/microsoft/quantum/tree/master/Numerics).</span></span>  <span data-ttu-id="041b1-150">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102)。</span><span class="sxs-lookup"><span data-stu-id="041b1-150">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102).</span></span>  

<span data-ttu-id="041b1-151">此版本重新组织、扩展并更新了化学库：</span><span class="sxs-lookup"><span data-stu-id="041b1-151">This release reorganizes extends and updates the chemistry library:</span></span>
* <span data-ttu-id="041b1-152">改进组件模块化、可扩展性和常规代码清理。</span><span class="sxs-lookup"><span data-stu-id="041b1-152">Improves modularity of components, extensibility, general code cleanup.</span></span>  <span data-ttu-id="041b1-153">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="041b1-153">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).</span></span>
* <span data-ttu-id="041b1-154">添加了对[多参考波函数](xref:microsoft.quantum.chemistry.concepts.multireference)（稀疏多参考波函数和单一耦合群集）的支持。</span><span class="sxs-lookup"><span data-stu-id="041b1-154">Add support for [multi-reference wavefunctions](xref:microsoft.quantum.chemistry.concepts.multireference), both sparse multi-reference wavefunctions and unitary coupled cluster.</span></span>  <span data-ttu-id="041b1-155">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="041b1-155">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>
* <span data-ttu-id="041b1-156">（谢谢！）[1QBit](https://1qbit.com) 参与者 ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit))：使用变分拟设的能量评估。</span><span class="sxs-lookup"><span data-stu-id="041b1-156">(Thank you!) [1QBit](https://1qbit.com) contributor ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Energy evaluation using variational ansatz.</span></span> <span data-ttu-id="041b1-157">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120)。</span><span class="sxs-lookup"><span data-stu-id="041b1-157">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120).</span></span>
* <span data-ttu-id="041b1-158">将 [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 架构更新为新[版本 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2)，并添加单一耦合群集规范。</span><span class="sxs-lookup"><span data-stu-id="041b1-158">Updating [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema to new [version 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), adding unitary coupled cluster specification.</span></span> <span data-ttu-id="041b1-159">[问题 #65](https://github.com/microsoft/QuantumLibraries/issues/65)。</span><span class="sxs-lookup"><span data-stu-id="041b1-159">[Issue #65](https://github.com/microsoft/QuantumLibraries/issues/65).</span></span>
* <span data-ttu-id="041b1-160">将 Python 互操作性添加到化学库函数。</span><span class="sxs-lookup"><span data-stu-id="041b1-160">Adding Python interoperability to chemistry library functions.</span></span> <span data-ttu-id="041b1-161">尝试此[示例](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration)。</span><span class="sxs-lookup"><span data-stu-id="041b1-161">Try out this [sample](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration).</span></span> <span data-ttu-id="041b1-162">[问题 #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="041b1-162">[Issue #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>

## <a name="version-061905"></a><span data-ttu-id="041b1-163">版本 0.6.1905</span><span class="sxs-lookup"><span data-stu-id="041b1-163">Version 0.6.1905</span></span>

<span data-ttu-id="041b1-164">发行日期：  2019 年 5 月 3 日</span><span class="sxs-lookup"><span data-stu-id="041b1-164">*Release date: May 3, 2019*</span></span>

<span data-ttu-id="041b1-165">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="041b1-165">This release contains the following:</span></span>
- <span data-ttu-id="041b1-166">更改 Q# 语言、</span><span class="sxs-lookup"><span data-stu-id="041b1-166">makes changes to the Q# language,</span></span> 
- <span data-ttu-id="041b1-167">重构量子开发工具包库、</span><span class="sxs-lookup"><span data-stu-id="041b1-167">restructures the Quantum Development Kit libraries,</span></span> 
- <span data-ttu-id="041b1-168">添加了新示例，以及</span><span class="sxs-lookup"><span data-stu-id="041b1-168">adds new samples, and</span></span> 
- <span data-ttu-id="041b1-169">修复 bug。</span><span class="sxs-lookup"><span data-stu-id="041b1-169">fixes bugs.</span></span>  <span data-ttu-id="041b1-170">适用于[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的多个已结束的 PR。</span><span class="sxs-lookup"><span data-stu-id="041b1-170">Several closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="041b1-171">此处汇总了这些更改，以及有关升级现有程序的说明。</span><span class="sxs-lookup"><span data-stu-id="041b1-171">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="041b1-172">有关这些更改的详细信息，请参阅 devblogs.microsoft.com/qsharp。</span><span class="sxs-lookup"><span data-stu-id="041b1-172">You can read more about these changes on devblogs.microsoft.com/qsharp.</span></span>

### <a name="q-language-syntax"></a><span data-ttu-id="041b1-173">Q# 语言语法</span><span class="sxs-lookup"><span data-stu-id="041b1-173">Q# language syntax</span></span>
<span data-ttu-id="041b1-174">此版本添加了新的 Q# 语言语法：</span><span class="sxs-lookup"><span data-stu-id="041b1-174">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="041b1-175">使用 `+` 运算符添加了[用于表示量子操作专用化的简单方式](xref:microsoft.quantum.language.type-model#functors)（控制和伴随）。</span><span class="sxs-lookup"><span data-stu-id="041b1-175">Add a [shorthand way to express specializations of quantum operations](xref:microsoft.quantum.language.type-model#functors) (control and adjoints) with `+` operators.</span></span>  <span data-ttu-id="041b1-176">旧语法已弃用。</span><span class="sxs-lookup"><span data-stu-id="041b1-176">The old syntax is deprecated.</span></span>  <span data-ttu-id="041b1-177">使用旧语法（例如 `: adjoint`）的程序将继续运行，但会生成编译时警告。</span><span class="sxs-lookup"><span data-stu-id="041b1-177">Programs that use the old syntax (e.g., `: adjoint`) will continue to work, but a compile time warning will be generated.</span></span>  
* <span data-ttu-id="041b1-178">添加了用于 [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) 的新运算符 `w/`，它可用于将数组创建表示为现有数组的修改。</span><span class="sxs-lookup"><span data-stu-id="041b1-178">Add a new operator for [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions), `w/`, can be used to express array creation as a modification of an existing array.</span></span>
* <span data-ttu-id="041b1-179">添加了常用 [apply-and-upate 语句](xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)，如 `+=`、`w/=`。</span><span class="sxs-lookup"><span data-stu-id="041b1-179">Add the common [apply-and-upate statement](xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols), e.g., `+=`, `w/=`.</span></span>
* <span data-ttu-id="041b1-180">添加了一种用于在[开放式指令](xref:microsoft.quantum.language.file-structure#open-directives)中指定命名空间短名称的方法。</span><span class="sxs-lookup"><span data-stu-id="041b1-180">Add a way to specify a short name for namespaces in [open directives](xref:microsoft.quantum.language.file-structure#open-directives).</span></span>

<span data-ttu-id="041b1-181">在此版本中，我们不再允许在 set 语句的左侧指定数组元素。</span><span class="sxs-lookup"><span data-stu-id="041b1-181">With this release, we no longer allow an array element to be specified on the left side of a set statement.</span></span>  <span data-ttu-id="041b1-182">这是因为该语法意味着数组在实际上是可变的，操作的结果始终是创建新数组并加以修改。</span><span class="sxs-lookup"><span data-stu-id="041b1-182">This is because that syntax implies that arrays are mutable when in fact, the result of the operation has always been the creation of a new array with the modification.</span></span>  <span data-ttu-id="041b1-183">系统将生成编译器错误，建议使用新新的 copy-and-update 运算符 `w/` 来达到相同的结果。</span><span class="sxs-lookup"><span data-stu-id="041b1-183">Instead, a compiler error will be generated with a suggestion to use the new copy-and-update operator, `w/`, to accomplish the same result.</span></span>  

### <a name="library-restructuring"></a><span data-ttu-id="041b1-184">库重构</span><span class="sxs-lookup"><span data-stu-id="041b1-184">Library restructuring</span></span>
<span data-ttu-id="041b1-185">此版本重新组织库，使它们的增长保持一致：</span><span class="sxs-lookup"><span data-stu-id="041b1-185">This release reorganizes the libraries to enable their growth in a consistent way:</span></span>
* <span data-ttu-id="041b1-186">将 Microsoft.Quantum.Primitive 命名空间重命名为 Microsoft.Quantum.Intrinsic。</span><span class="sxs-lookup"><span data-stu-id="041b1-186">Renames the Microsoft.Quantum.Primitive namespace  to Microsoft.Quantum.Intrinsic.</span></span>  <span data-ttu-id="041b1-187">这些操作由目标计算机实现。</span><span class="sxs-lookup"><span data-stu-id="041b1-187">These operations are implemented by the target machine.</span></span>  <span data-ttu-id="041b1-188">Microsoft.Quantum.Primitive 命名空间已弃用。</span><span class="sxs-lookup"><span data-stu-id="041b1-188">The Microsoft.Quantum.Primitive namespace is deprecated.</span></span>  <span data-ttu-id="041b1-189">运行时警告将建议程序何时使用弃用的名称来调用操作和函数。</span><span class="sxs-lookup"><span data-stu-id="041b1-189">A runtime warning will advise when programs call operations and functions using deprecated names.</span></span>

* <span data-ttu-id="041b1-190">将 Microsoft.Quantum.Canon 包重命名为 Microsoft.Quantum.Standard。</span><span class="sxs-lookup"><span data-stu-id="041b1-190">Renames the Microsoft.Quantum.Canon package to Microsoft.Quantum.Standard.</span></span>  <span data-ttu-id="041b1-191">此包中包含大多数 Q# 程序共用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="041b1-191">This package contains namespaces that are common to most Q# programs.</span></span>  <span data-ttu-id="041b1-192">这包括：</span><span class="sxs-lookup"><span data-stu-id="041b1-192">This includes:</span></span>  
    - <span data-ttu-id="041b1-193">Microsoft.Quantum.Canon，适合常见操作</span><span class="sxs-lookup"><span data-stu-id="041b1-193">Microsoft.Quantum.Canon for common operations</span></span>
    - <span data-ttu-id="041b1-194">Microsoft.Quantum.Arithmetic，适合常规算术操作</span><span class="sxs-lookup"><span data-stu-id="041b1-194">Microsoft.Quantum.Arithmetic for general purpose arithmetic operations</span></span>
    - <span data-ttu-id="041b1-195">Microsoft.Quantum.Preparation，适合用于准备量子位状态的操作</span><span class="sxs-lookup"><span data-stu-id="041b1-195">Microsoft.Quantum.Preparation for operations used to prepare qubit state</span></span>
    - <span data-ttu-id="041b1-196">Microsoft.Quantum.Simulation，适合模拟函数</span><span class="sxs-lookup"><span data-stu-id="041b1-196">Microsoft.Quantum.Simulation for simulation functionality</span></span>

<span data-ttu-id="041b1-197">进行此更改后，如果程序包含适用于 Microsoft.Quatum.Canon 命名空间的单个“open”语句，且引用了已移至其他三个新命名空间的操作，则可能会遇到生成错误。</span><span class="sxs-lookup"><span data-stu-id="041b1-197">With this change, programs that include a single "open" statement for the namespace Microsoft.Quatum.Canon may encounter build errors if the program references operations that were moved to the other three new namespaces.</span></span>  <span data-ttu-id="041b1-198">为三个新的命名空间添加其他 open 语句是解决此问题的直接方法。</span><span class="sxs-lookup"><span data-stu-id="041b1-198">Adding the additional open statements for the three new namespaces is a straightforward way to resolve this issue.</span></span>  

* <span data-ttu-id="041b1-199">已弃用几个命名空间，因为其中的操作已重新组织到其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="041b1-199">Several namespaces have been deprecated as the operations within have been reorganized to other namespaces.</span></span> <span data-ttu-id="041b1-200">使用这些命名空间的程序将继续运行，并且编译时警告将指示在其中定义操作的命名空间。</span><span class="sxs-lookup"><span data-stu-id="041b1-200">Programs that use these namespaces will continue to work, and a compile time warning will denote the namespace where the operation is defined.</span></span>  

* <span data-ttu-id="041b1-201">Microsoft.Quantum.Arithmetic 命名空间已标准化为使用 <xref:microsoft.quantum.arithmetic.littleendian> 用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="041b1-201">The Microsoft.Quantum.Arithmetic namespace has been normalized to use the <xref:microsoft.quantum.arithmetic.littleendian> user-defined type.</span></span> <span data-ttu-id="041b1-202">需要转换为小端时，请使用函数 [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian)。</span><span class="sxs-lookup"><span data-stu-id="041b1-202">Use the function [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) when needed to convert to little endian.</span></span>  

* <span data-ttu-id="041b1-203">几个可调用对象（函数和操作）的名称已更改，符合 [Q# 风格指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="041b1-203">The names of several callables (functions and operations) have been changed to conform to the [Q# Style Guide](xref:microsoft.quantum.contributing.style).</span></span>  <span data-ttu-id="041b1-204">旧的可调用对象的名称已弃用。</span><span class="sxs-lookup"><span data-stu-id="041b1-204">The old callable names are deprecated.</span></span>  <span data-ttu-id="041b1-205">使用旧的可调用对象的程序将继续处理编译时警告。</span><span class="sxs-lookup"><span data-stu-id="041b1-205">Programs that use the old callables will continue to work with a compile time warning.</span></span> 

### <a name="new-samples"></a><span data-ttu-id="041b1-206">新示例</span><span class="sxs-lookup"><span data-stu-id="041b1-206">New Samples</span></span>

<span data-ttu-id="041b1-207">我们已添加 [Q# 与 F# 驱动程序结合使用的示例](https://github.com/Microsoft/Quantum/pull/164)。</span><span class="sxs-lookup"><span data-stu-id="041b1-207">We added a [sample of using Q# with F# driver](https://github.com/Microsoft/Quantum/pull/164).</span></span>  

<span data-ttu-id="041b1-208">谢谢你们  ：</span><span class="sxs-lookup"><span data-stu-id="041b1-208">**Thank you!**</span></span> <span data-ttu-id="041b1-209">在 http://github.com/Microsoft/Quantum 向我们的开放代码库发布内容的以下参与者。</span><span class="sxs-lookup"><span data-stu-id="041b1-209">to the following contributor to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="041b1-210">这些内容极大地丰富了 Q# 代码的示例：</span><span class="sxs-lookup"><span data-stu-id="041b1-210">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="041b1-211">Mathias Soeken ([@msoeken](https://github.com/msoeken))：Oracle 函数合成。</span><span class="sxs-lookup"><span data-stu-id="041b1-211">Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle function synthesis.</span></span> <span data-ttu-id="041b1-212">[PR #135](https://github.com/Microsoft/Quantum/pull/135)。</span><span class="sxs-lookup"><span data-stu-id="041b1-212">[PR #135](https://github.com/Microsoft/Quantum/pull/135).</span></span>

### <a name="migrating-existing-projects-to-061905"></a><span data-ttu-id="041b1-213">将现有项目迁移到 0.6.1905。</span><span class="sxs-lookup"><span data-stu-id="041b1-213">Migrating existing projects to 0.6.1905.</span></span>

<span data-ttu-id="041b1-214">请参阅[安装指南](xref:microsoft.quantum.install)，以更新 QDK。</span><span class="sxs-lookup"><span data-stu-id="041b1-214">See the [install guide](xref:microsoft.quantum.install) to update the QDK.</span></span>
  
<span data-ttu-id="041b1-215">如果现有 Q# 项目源自量子开发工具包 0.5 版，则下方介绍了将这些项目迁移到最新版本的步骤。</span><span class="sxs-lookup"><span data-stu-id="041b1-215">If you have existing Q# projects from version 0.5 of the Quantum Development Kit, the following are the steps to migrate those projects to the newest version.</span></span>

    1. <span data-ttu-id="041b1-216">项目需要按顺序升级。</span><span class="sxs-lookup"><span data-stu-id="041b1-216">Projects need to be upgraded in order.</span></span>  <span data-ttu-id="041b1-217">如果解决方案包含多个项目，请按引用顺序更新每个项目。</span><span class="sxs-lookup"><span data-stu-id="041b1-217">If you have a solution with multiple projects, update each project in the order they are referenced.</span></span>
    2. <span data-ttu-id="041b1-218">在命令行中，运行 `dotnet clean`，删除所有现有的二进制文件和中间文件。</span><span class="sxs-lookup"><span data-stu-id="041b1-218">From a command line, Run `dotnet clean` to remove all existing binaries and intermediate files.</span></span>
    3. <span data-ttu-id="041b1-219">在文本编辑器中，编辑 .csproj 文件，将所有“Microsoft.Quantum”`PackageReference` 的版本更改为版本 0.6.1904，并将“Microsoft.Quantum.Canon”包名称更改为“Microsoft.Quantum.Standard”，例如：</span><span class="sxs-lookup"><span data-stu-id="041b1-219">In a text editor, edit the .csproj file to change the version of all the "Microsoft.Quantum" `PackageReference` to version 0.6.1904, and change the "Microsoft.Quantum.Canon" package name to "Microsoft.Quantum.Standard", for example:</span></span>

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. <span data-ttu-id="041b1-220">从命令行运行以下命令：`dotnet msbuild`</span><span class="sxs-lookup"><span data-stu-id="041b1-220">From the command line, run this command: `dotnet msbuild`</span></span>  
    5. <span data-ttu-id="041b1-221">运行此命令后，可能仍需要手动解决因上述更改所导致的错误。</span><span class="sxs-lookup"><span data-stu-id="041b1-221">After running this, you might still need to manually address errors due to changes listed above.</span></span>  <span data-ttu-id="041b1-222">在许多情况下，Visual Studio 或 Visual Studio Code 中的 IntelliSense 会报告这些错误。</span><span class="sxs-lookup"><span data-stu-id="041b1-222">In many cases, these errors will also be reported by IntelliSense in Visual Studio or Visual Studio Code.</span></span>
        - <span data-ttu-id="041b1-223">在 Visual Studio 2019 或 Visual Studio Code 中，打开项目的根文件夹或包含的解决方案。</span><span class="sxs-lookup"><span data-stu-id="041b1-223">Open the root folder of the project or the containing solution in Visual Studio 2019 or Visual Studio Code.</span></span>
        - <span data-ttu-id="041b1-224">在编辑器中打开 .qs 文件后，输出窗口应显示 Q# 语言扩展的输出。</span><span class="sxs-lookup"><span data-stu-id="041b1-224">After opening a .qs file in the editor, you should see the output of the Q# language extension in the output window.</span></span>
        - <span data-ttu-id="041b1-225">成功加载项目后（输出窗口中会出现相应指示），打开每个文件并手动解决所有剩余问题。</span><span class="sxs-lookup"><span data-stu-id="041b1-225">After the project has loaded successfully (indicated in the output window) open each file and manually to address all remaining issues.</span></span>

> [!NOTE]
> * <span data-ttu-id="041b1-226">对于0.6 版本，量子开发工具包附带的语言服务器不支持多个工作区。</span><span class="sxs-lookup"><span data-stu-id="041b1-226">For the 0.6 release, the language server included with the Quantum Development Kit does not support multiple workspaces.</span></span>
> * <span data-ttu-id="041b1-227">若要在 Visual Studio Code 中处理项目，请打开包含项目本身和所有引用项目的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="041b1-227">In order to work with a project in Visual Studio Code, open the root folder containing the project itself and all referenced projects.</span></span>   
> * <span data-ttu-id="041b1-228">若要在 Visual Studio 中处理解决方案，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="041b1-228">In order to work with a solution in Visual Studio, all projects contained in the solution need to be in the same folder as the solution or in one of its subfolders.</span></span>  
> * <span data-ttu-id="041b1-229">不支持在迁移到 0.6 和更高版本的项目与使用较低版本的包的项目之间进行引用  。</span><span class="sxs-lookup"><span data-stu-id="041b1-229">References between projects migrated to 0.6 and higher and projects using older package versions are **not** supported.</span></span>

## <a name="version-051904"></a><span data-ttu-id="041b1-230">版本 0.5.1904</span><span class="sxs-lookup"><span data-stu-id="041b1-230">Version 0.5.1904</span></span>

<span data-ttu-id="041b1-231">发行日期：  2019 年 4 月 15 日</span><span class="sxs-lookup"><span data-stu-id="041b1-231">*Release date: April 15, 2019*</span></span>

<span data-ttu-id="041b1-232">此版本包含 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="041b1-232">This release contains bug fixes.</span></span>


## <a name="version-051903"></a><span data-ttu-id="041b1-233">版本 0.5.1903</span><span class="sxs-lookup"><span data-stu-id="041b1-233">Version 0.5.1903</span></span>

<span data-ttu-id="041b1-234">发行日期：  2019 年 3 月 27 日</span><span class="sxs-lookup"><span data-stu-id="041b1-234">*Release date: March 27, 2019*</span></span>

<span data-ttu-id="041b1-235">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="041b1-235">This release contains the following:</span></span>

- <span data-ttu-id="041b1-236">添加了对 Jupyter Notebook 的支持，可以更好地了解 Q#。</span><span class="sxs-lookup"><span data-stu-id="041b1-236">Adds support for Jupyter Notebook, which offers a great way to learn about Q#.</span></span>  <span data-ttu-id="041b1-237">[查看新的 Jupyter Notebook 示例，并了解如何编写自己的 Notebooks](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="041b1-237">[Check out new Jupyter Notebook samples and learn how to write your own Notebooks](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="041b1-238">将整数加法器算法添加到了量子 Canon 库中。</span><span class="sxs-lookup"><span data-stu-id="041b1-238">Adds integer adder arithmetic to the Quantum Canon library.</span></span>  <span data-ttu-id="041b1-239">另请参阅[描述如何使用新的整数加法器](https://github.com/Microsoft/Quantum/blob/master/Samples/src/Arithmetic/Adder%20Example.ipynb)的 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="041b1-239">See also a Jupyter Notebook that [describes how to use the new integer adders](https://github.com/Microsoft/Quantum/blob/master/Samples/src/Arithmetic/Adder%20Example.ipynb).</span></span>

- <span data-ttu-id="041b1-240">针对社区报告的 DumpRegister 问题的 bug 修复 ([#148](https://github.com/Microsoft/Quantum/issues/148))。</span><span class="sxs-lookup"><span data-stu-id="041b1-240">Bug fix for DumpRegister issue reported by the community ([#148](https://github.com/Microsoft/Quantum/issues/148)).</span></span>

- <span data-ttu-id="041b1-241">添加了从 [using 语句](xref:microsoft.quantum.language.statements)中返回的功能。</span><span class="sxs-lookup"><span data-stu-id="041b1-241">Added ability to return from within a [using statement](xref:microsoft.quantum.language.statements).</span></span>

- <span data-ttu-id="041b1-242">改版了[入门指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="041b1-242">Revamped [getting started guide](xref:microsoft.quantum.install).</span></span>


## <a name="version-051902"></a><span data-ttu-id="041b1-243">版本 0.5.1902</span><span class="sxs-lookup"><span data-stu-id="041b1-243">Version 0.5.1902</span></span>

<span data-ttu-id="041b1-244">发行日期：  2019 年 2 月 27 日</span><span class="sxs-lookup"><span data-stu-id="041b1-244">*Release date: February 27, 2019*</span></span>

<span data-ttu-id="041b1-245">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="041b1-245">This release contains the following:</span></span>

- <span data-ttu-id="041b1-246">添加了对跨平台 Python 主机的支持。</span><span class="sxs-lookup"><span data-stu-id="041b1-246">Adds support for a cross-platform Python host.</span></span>  <span data-ttu-id="041b1-247">使用 Python 的 `qsharp` 包可以轻松地从 Python 内模拟 Q# 操作和函数。</span><span class="sxs-lookup"><span data-stu-id="041b1-247">The `qsharp` package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="041b1-248">了解有关 [Python 互操作性](xref:microsoft.quantum.install)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-248">Learn more about [Python interoperability](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="041b1-249">Visual Studio 和 Visual Studio Code 扩展现支持符号重命名（例如，函数和操作）。</span><span class="sxs-lookup"><span data-stu-id="041b1-249">The Visual Studio and Visual Studio Code extensions now support renaming of symbols (e.g., functions and operations).</span></span>

- <span data-ttu-id="041b1-250">Visual Studio 扩展现可安装在 Visual Studio 2019 上。</span><span class="sxs-lookup"><span data-stu-id="041b1-250">The Visual Studio extension can now be installed on Visual Studio 2019.</span></span>

## <a name="version-041901"></a><span data-ttu-id="041b1-251">版本 0.4.1901</span><span class="sxs-lookup"><span data-stu-id="041b1-251">Version 0.4.1901</span></span>

<span data-ttu-id="041b1-252">发行日期：  2019 年 1 月 30 日</span><span class="sxs-lookup"><span data-stu-id="041b1-252">*Release date: January 30, 2019*</span></span>

<span data-ttu-id="041b1-253">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="041b1-253">This release contains the following:</span></span>

- <span data-ttu-id="041b1-254">添加了对新的基元类型 BigInt 的支持，该类型表示任意大小的有符号整数。</span><span class="sxs-lookup"><span data-stu-id="041b1-254">adds support for a new primitive type, BigInt, which represents a signed integer of arbitrary size.</span></span>  <span data-ttu-id="041b1-255">了解有关 [BigInt 类型](xref:microsoft.quantum.language.type-model)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-255">Learn more about [BigInt type](xref:microsoft.quantum.language.type-model).</span></span>
- <span data-ttu-id="041b1-256">添加了新的 Toffoli 模拟器，这是一种特殊用途的快速模拟器，可模拟 X、CNOT 和多方控制 X 量子操作（具有大量的量子位）。</span><span class="sxs-lookup"><span data-stu-id="041b1-256">adds new Toffoli simulator, a special purpose fast simulator that can simulate X, CNOT and multi-controlled X quantum operations with very large numbers of qubits.</span></span>  <span data-ttu-id="041b1-257">了解有关 [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-257">Learn more about [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator).</span></span>
- <span data-ttu-id="041b1-258">添加了一种简单的资源估计器，用于估计在量子计算机上运行给定的 Q# 操作实例所需的资源。</span><span class="sxs-lookup"><span data-stu-id="041b1-258">adds a simple resource estimator that estimates the resources required to run a given instancee of a Q# operation on a quantum computer.</span></span>  <span data-ttu-id="041b1-259">了解有关[资源估计器](xref:microsoft.quantum.machines.resources-estimator)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-259">Learn more about the [Resource Estimator](xref:microsoft.quantum.machines.resources-estimator).</span></span>


## <a name="version-0318112802"></a><span data-ttu-id="041b1-260">版本 0.3.1811.2802</span><span class="sxs-lookup"><span data-stu-id="041b1-260">Version 0.3.1811.2802</span></span>

<span data-ttu-id="041b1-261">发行日期：  2018 年 11 月 28 日</span><span class="sxs-lookup"><span data-stu-id="041b1-261">*Release date: November 28, 2018*</span></span>

<span data-ttu-id="041b1-262">尽管 VS Code 扩展未使用它，但在与 `event-stream` NPM 包相关的 [扩展清除](https://code.visualstudio.com/blogs/2018/11/26/event-stream)过程中，它已被标记并从商城中删除。</span><span class="sxs-lookup"><span data-stu-id="041b1-262">Even though our VS Code extension was not using it, it was flagged and removed from the marketplace during [the extensions purge](https://code.visualstudio.com/blogs/2018/11/26/event-stream) related to the `event-stream` NPM package.</span></span> <span data-ttu-id="041b1-263">此版本删除了所有可使扩展触发任何红色标记的运行时依赖项。</span><span class="sxs-lookup"><span data-stu-id="041b1-263">This version removes all runtime dependencies that could make the extension trigger any red flags.</span></span>

<span data-ttu-id="041b1-264">如果以前安装了该扩展，则需要访问 Visual Studio Marketplace 上[适用于 Visual Studio Code 的 Microsoft 量子开发工具包](vscode:extension/quantum.quantum-devkit-vscode)扩展并按“安装”，再次安装该扩展。</span><span class="sxs-lookup"><span data-stu-id="041b1-264">If you had previously installed the extension you will need to install it again by visiting the [Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) extension on the Visual Studio Marketplace and press Install.</span></span> <span data-ttu-id="041b1-265">对此产生的不便，我们深表歉意。</span><span class="sxs-lookup"><span data-stu-id="041b1-265">We are sorry about the inconvenience.</span></span>


## <a name="version-0318111511"></a><span data-ttu-id="041b1-266">版本 0.3.1811.1511</span><span class="sxs-lookup"><span data-stu-id="041b1-266">Version 0.3.1811.1511</span></span>

<span data-ttu-id="041b1-267">发行日期：  2018 年 11 月 20 日</span><span class="sxs-lookup"><span data-stu-id="041b1-267">*Release date: November 20, 2018*</span></span>

<span data-ttu-id="041b1-268">此版本修复了阻止某些用户成功加载 Visual Studio 扩展的 bug。</span><span class="sxs-lookup"><span data-stu-id="041b1-268">This release fixes a bug that prevented some users to successfully load the Visual Studio extension.</span></span>

<span data-ttu-id="041b1-269">如果要从 0.2 版本的量子开发工具包升级，请了解有关 [Q# 语言更改和迁移 Q# 程序](xref:microsoft.quantum.relnotes.migration-0-3)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-269">If you are upgrading from a 0.2 version of the Quantum Development Kit, learn more about [Q# language changes and migrating your Q# program](xref:microsoft.quantum.relnotes.migration-0-3).</span></span>

## <a name="version-031811203"></a><span data-ttu-id="041b1-270">版本 0.3.1811.203</span><span class="sxs-lookup"><span data-stu-id="041b1-270">Version 0.3.1811.203</span></span>

<span data-ttu-id="041b1-271">发行日期：  2018 年 11 月 2 日</span><span class="sxs-lookup"><span data-stu-id="041b1-271">*Release date: November 2, 2018*</span></span>

<span data-ttu-id="041b1-272">此版本包含几个 bug 修复，其中包括：</span><span class="sxs-lookup"><span data-stu-id="041b1-272">This release includes a few bug fixes, including:</span></span>

* <span data-ttu-id="041b1-273">调用 `DumpMachine` 可能会在某些情况下更改模拟器的状态。</span><span class="sxs-lookup"><span data-stu-id="041b1-273">Invoking `DumpMachine` could change the state of the simulator under certain situations.</span></span>
* <span data-ttu-id="041b1-274">删除了使用比 2.1.403 更低的 .NET Core 版本生成项目时的编译警告。</span><span class="sxs-lookup"><span data-stu-id="041b1-274">Removed compilation warnings when building projects using a version of .NET Core previous to 2.1.403.</span></span>
* <span data-ttu-id="041b1-275">清理文档，特别是将鼠标悬停在 VS Code 或 Visual Studio 时所显示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="041b1-275">Clean up of documentation, specially the tooltips shown during mouse hover in VS Code or Visual Studio.</span></span>

<span data-ttu-id="041b1-276">如果要从 0.2 版本的量子开发工具包升级，请了解有关 [Q# 语言更改和迁移 Q# 程序](xref:microsoft.quantum.relnotes.migration-0-3)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-276">If you are upgrading from a 0.2 version of the Quantum Development Kit, learn more about [Q# language changes and migrating your Q# program](xref:microsoft.quantum.relnotes.migration-0-3).</span></span>

## <a name="version-0318102508"></a><span data-ttu-id="041b1-277">版本 0.3.1810.2508</span><span class="sxs-lookup"><span data-stu-id="041b1-277">Version 0.3.1810.2508</span></span>

<span data-ttu-id="041b1-278">发行日期：  2018 年 10 月 29 日</span><span class="sxs-lookup"><span data-stu-id="041b1-278">*Release date: October 29, 2018*</span></span>

<span data-ttu-id="041b1-279">此版本包含新的语言功能和改善的开发者体验：</span><span class="sxs-lookup"><span data-stu-id="041b1-279">This release includes new language features and an improved developer experience:</span></span>

* <span data-ttu-id="041b1-280">此版本包括用于 Q# 的语言服务器，以及用于 Visual Studio 和 Visual Studio Code 的客户端集成。</span><span class="sxs-lookup"><span data-stu-id="041b1-280">This release includes a language server for Q#, as well as the client integrations for Visual Studio and Visual Studio Code.</span></span> <span data-ttu-id="041b1-281">这会启用一组新的 IntelliSense 功能，以及在键入时以波浪下划线的形式发出错误和警告的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="041b1-281">This enables a new set of IntelliSense features along with live feedback on typing in form of squiggly underlinings of errors and warnings.</span></span> 
* <span data-ttu-id="041b1-282">总体上看，此更新极大地改善了诊断消息，可以轻松地导航到诊断消息的准确范围，并在显示的悬停信息中提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-282">This update greatly improves diagnostic messages in general, with easy navigation to and precise ranges for diagnostics and additional details in the displayed hover information.</span></span>
* <span data-ttu-id="041b1-283">Q# 语言经扩展后，统一了开发者可以执行常见操作的方式和增强语言功能的方式，从而有效地表达量子计算。</span><span class="sxs-lookup"><span data-stu-id="041b1-283">The Q# language has been extended in ways that unifies the ways developers can do common operations and new enhancements to the language features to powerfully express quantum computation.</span></span>  <span data-ttu-id="041b1-284">此版本中的 Q# 语言进行了一些的重大更改。</span><span class="sxs-lookup"><span data-stu-id="041b1-284">There are a handful of breaking changes to the Q# language with this release.</span></span>   

<span data-ttu-id="041b1-285">了解有关 [Q# 语言更改和迁移 Q# 程序](xref:microsoft.quantum.relnotes.migration-0-3)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-285">Learn more about [Q# language changes and migrating your Q# program](xref:microsoft.quantum.relnotes.migration-0-3).</span></span>

<span data-ttu-id="041b1-286">此版本还包括新的量子化学库：</span><span class="sxs-lookup"><span data-stu-id="041b1-286">This release also includes a new quantum chemistry library:</span></span>

* <span data-ttu-id="041b1-287">该化学库包含新的 Hamiltonian 模拟功能，其中包括：</span><span class="sxs-lookup"><span data-stu-id="041b1-287">The chemistry library contains new Hamiltonian simulation features, including:</span></span>
    - <span data-ttu-id="041b1-288">任意偶数顺序的 Trotter–Suzuki 积分器，可提高模拟准确性。</span><span class="sxs-lookup"><span data-stu-id="041b1-288">Trotter–Suzuki integrators of arbitrary even order for improved simulation accuracy.</span></span>
    - <span data-ttu-id="041b1-289">量子位化模拟技术，其中进行了特定于化学的优化，可降低 $T$-gate 复杂性。</span><span class="sxs-lookup"><span data-stu-id="041b1-289">Qubitization simulation technique with chemistry-specific optimizations for reducing $T$-gate complexity.</span></span>
* <span data-ttu-id="041b1-290">引入了一种新的开源架构，称为 Broombridge 架构（该名称参考了被誉为 Hamiltonians 发源地的[地标](https://en.wikipedia.org/wiki/Broom_Bridge)），用于导入分子表示形式并对其进行模拟。</span><span class="sxs-lookup"><span data-stu-id="041b1-290">A new open source schema, called Broombridge Schema (in reference to a [landmark](https://en.wikipedia.org/wiki/Broom_Bridge) celebrated as a birthplace of Hamiltonians), is introduced for importing representations of molecules and simulating them.</span></span>
* <span data-ttu-id="041b1-291">提供使用 Broombridge 架构定义的多个化学表示形式。</span><span class="sxs-lookup"><span data-stu-id="041b1-291">Multiple chemical representations defined using the Broombridge Schema are provided.</span></span>  <span data-ttu-id="041b1-292">这些模型由一种开源的高性能计算化学工具 [NWChem](http://www.nwchem-sw.org/) 生成。</span><span class="sxs-lookup"><span data-stu-id="041b1-292">These models were generated by [NWChem](http://www.nwchem-sw.org/), an open source high-performance computational chemistry tool.</span></span>
* <span data-ttu-id="041b1-293">教程和示例介绍如何使用化学库和 Broombridge 数据模型执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="041b1-293">Tutorials and Samples describe how to use the chemistry library and the Broombridge data models to:</span></span>
    - <span data-ttu-id="041b1-294">使用化学库构造简单的 Hamiltonians</span><span class="sxs-lookup"><span data-stu-id="041b1-294">Construct simple Hamiltonians using the chemistry library</span></span>
    - <span data-ttu-id="041b1-295">使用阶段估计直观显示氢化锂的基态能量和激发态能量。</span><span class="sxs-lookup"><span data-stu-id="041b1-295">Visualize ground and excited energies of Lithium Hydride using phase estimation.</span></span>
    - <span data-ttu-id="041b1-296">执行量子化学模拟的资源评估。</span><span class="sxs-lookup"><span data-stu-id="041b1-296">Perform resource estimates of quantum chemistry simulation.</span></span>
    - <span data-ttu-id="041b1-297">估计 Broombridge 架构表示的分子的能级。</span><span class="sxs-lookup"><span data-stu-id="041b1-297">Estimate energy levels of molecules represented by the Broombridge schema.</span></span>
* <span data-ttu-id="041b1-298">文档介绍如何使用 NWChem 生成其他化学模型，以使用 Q# 进行量子模拟。</span><span class="sxs-lookup"><span data-stu-id="041b1-298">Documentation describes how to use NWChem to generate additional chemical models for quantum simulation with Q#.</span></span>

<span data-ttu-id="041b1-299">了解有关[量子开发工具包化学库](xref:microsoft.quantum.chemistry.concepts.intro)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-299">Learn more about the [Quantum Development Kit chemistry library](xref:microsoft.quantum.chemistry.concepts.intro).</span></span>

<span data-ttu-id="041b1-300">使用新的化学库，我们将库划分成新的 GitHub 存储库 [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries)。</span><span class="sxs-lookup"><span data-stu-id="041b1-300">With the new chemistry library, we are separating out the libraries into a new GitHub repo, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).</span></span>  <span data-ttu-id="041b1-301">示例保留在 [Microsoft/Quantum](https://github.com/Microsoft/Quantum) 存储库中。</span><span class="sxs-lookup"><span data-stu-id="041b1-301">The samples remain in the repo [Microsoft/Quantum](https://github.com/Microsoft/Quantum).</span></span>  <span data-ttu-id="041b1-302">我们欢迎大家参与到这两个库的构建中！</span><span class="sxs-lookup"><span data-stu-id="041b1-302">We welcome contributions to both!</span></span>

<span data-ttu-id="041b1-303">此版本包括社区报告的问题对应的 bug 修复和功能：</span><span class="sxs-lookup"><span data-stu-id="041b1-303">This release includes bug fixes and features for issues reported by the community:</span></span>

* <span data-ttu-id="041b1-304">Intellisense for Q#？</span><span class="sxs-lookup"><span data-stu-id="041b1-304">Intellisense for Q#?</span></span> <span data-ttu-id="041b1-305">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918))。</span><span class="sxs-lookup"><span data-stu-id="041b1-305">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).</span></span>
* <span data-ttu-id="041b1-306">.qs 文件 ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049))。</span><span class="sxs-lookup"><span data-stu-id="041b1-306">.qs files ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).</span></span>
* <span data-ttu-id="041b1-307">当 if 语句中大括号缩写时，请改进错误消息 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518))。</span><span class="sxs-lookup"><span data-stu-id="041b1-307">Improve error message when curly braces are abbreviated in if statement ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).</span></span>
* <span data-ttu-id="041b1-308">支持在可变（重新）绑定上进行元组析构 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444))。</span><span class="sxs-lookup"><span data-stu-id="041b1-308">Support tuple deconstruction at mutable (re-)binding ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).</span></span>
* <span data-ttu-id="041b1-309">运行提供的 BitFlipCode 时出错 ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="041b1-309">Error Running Provided BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>
* <span data-ttu-id="041b1-310">H2SimulationGUI 有时会显示较大峰值 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370))。</span><span class="sxs-lookup"><span data-stu-id="041b1-310">H2SimulationGUI displays big peaks sometimes ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="041b1-311">社区贡献</span><span class="sxs-lookup"><span data-stu-id="041b1-311">Community Contributions</span></span>

<span data-ttu-id="041b1-312">谢谢你们  ：</span><span class="sxs-lookup"><span data-stu-id="041b1-312">**Thank you!**</span></span> <span data-ttu-id="041b1-313">在 http://github.com/Microsoft/Quantum 向我们的开放代码库发布内容的以下参与者。</span><span class="sxs-lookup"><span data-stu-id="041b1-313">to the following contributors to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="041b1-314">这些内容极大地丰富了 Q# 代码的示例：</span><span class="sxs-lookup"><span data-stu-id="041b1-314">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="041b1-315">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman))：通过创建 QASM 到 Q# 的转换器，改善了 QASM/Q# 开发者的体验。</span><span class="sxs-lookup"><span data-stu-id="041b1-315">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Improved the experience for QASM/Q# developers by creating a QASM to Q# translator.</span></span> <span data-ttu-id="041b1-316">[PR #58](https://github.com/Microsoft/Quantum/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="041b1-316">[PR #58](https://github.com/Microsoft/Quantum/pull/58).</span></span>

* <span data-ttu-id="041b1-317">Andrew Helwer ([@ahelwer](https://github.com/ahelwer))：提供了实现 CHSH 游戏的示例，该游戏是一个与非区域相关的量子游戏。</span><span class="sxs-lookup"><span data-stu-id="041b1-317">Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Contributed a sample implementing the CHSH Game, a quantum game related to non-locality.</span></span>  <span data-ttu-id="041b1-318">[PR #84](https://github.com/Microsoft/Quantum/pull/84)。</span><span class="sxs-lookup"><span data-stu-id="041b1-318">[PR #84](https://github.com/Microsoft/Quantum/pull/84).</span></span>

<span data-ttu-id="041b1-319">同样感谢 Rohit Gupta（[@guptarohit](https://github.com/guptarohit)，[PR #90](https://github.com/Microsoft/quantum/pull/90)）、Tanaka Takayoshi（[@tanaka-takayoshi](https://github.com/tanaka-takayoshi)，[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)），以及 Lee James O'Riordan（[@mlxd](https://github.com/mlxd)，[PR #96](https://github.com/Microsoft/Quantum/pull/96)），他们通过分类文档以及更正拼写和错误改善了我们所有人的内容！</span><span class="sxs-lookup"><span data-stu-id="041b1-319">Thank you also to Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)), and Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) for their work improving the content for all of us through documentation, spelling and typo corrections!</span></span> 

## <a name="version-021809701"></a><span data-ttu-id="041b1-320">版本 0.2.1809.701</span><span class="sxs-lookup"><span data-stu-id="041b1-320">Version 0.2.1809.701</span></span>

<span data-ttu-id="041b1-321">发行日期：  2018 年 9 月 10 日</span><span class="sxs-lookup"><span data-stu-id="041b1-321">*Release date: September 10, 2018*</span></span>

<span data-ttu-id="041b1-322">此版本包括社区报告的问题对应的 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="041b1-322">This release includes bug fixes for issues reported by the community.</span></span> <span data-ttu-id="041b1-323">其中包括：</span><span class="sxs-lookup"><span data-stu-id="041b1-323">Including:</span></span>

* <span data-ttu-id="041b1-324">无法使用移位运算符 ([GitHub](https://github.com/Microsoft/Quantum/issues/75))。</span><span class="sxs-lookup"><span data-stu-id="041b1-324">Unable to use shift operator ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).</span></span>
* <span data-ttu-id="041b1-325">打印到控制台时，`DumpMachine` / `DumpRegister` 在 `QCTraceSimulator` 上失败 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680))。</span><span class="sxs-lookup"><span data-stu-id="041b1-325">`DumpMachine` / `DumpRegister` fails on `QCTraceSimulator` when printing to console ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).</span></span>
* <span data-ttu-id="041b1-326">允许分配 0 个量子位 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits))。</span><span class="sxs-lookup"><span data-stu-id="041b1-326">Allow allocating 0 qubits ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).</span></span>
* <span data-ttu-id="041b1-327">`AssertQubitState` 需要显式 Complex() 调用 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call))。</span><span class="sxs-lookup"><span data-stu-id="041b1-327">`AssertQubitState` requires explicit Complex() call ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).</span></span>
* <span data-ttu-id="041b1-328">`Measure` 操作始终在 macOS 上返回 `One` ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="041b1-328">`Measure` operation always returns `One` on macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>

<span data-ttu-id="041b1-329">谢谢！</span><span class="sxs-lookup"><span data-stu-id="041b1-329">Thanks!</span></span> 

## <a name="version-0218063001"></a><span data-ttu-id="041b1-330">版本 0.2.1806.3001</span><span class="sxs-lookup"><span data-stu-id="041b1-330">Version 0.2.1806.3001</span></span>

<span data-ttu-id="041b1-331">发行日期：  2018 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="041b1-331">*Release date: June 30, 2018*</span></span>

<span data-ttu-id="041b1-332">此版本只是对 [GitHub 上报告的 #48 问题](https://github.com/Microsoft/Quantum/issues/48)的快速修复（如果用户名包含空格，则 Q# 编译失败）。</span><span class="sxs-lookup"><span data-stu-id="041b1-332">This releases is just a quick fix for [issue #48 reported on GitHub](https://github.com/Microsoft/Quantum/issues/48) (Q# compilation fails if user name contains a blank space).</span></span> <span data-ttu-id="041b1-333">在相应的新版本 (`0.2.1806.3001-preview`) 中遵循与 `0.2.1806.1503` 相同的更新说明。</span><span class="sxs-lookup"><span data-stu-id="041b1-333">Follow same update instructions as `0.2.1806.1503` with the corresponding new version (`0.2.1806.3001-preview`).</span></span>

## <a name="version-0218061503"></a><span data-ttu-id="041b1-334">版本 0.2.1806.1503</span><span class="sxs-lookup"><span data-stu-id="041b1-334">Version 0.2.1806.1503</span></span>

<span data-ttu-id="041b1-335">发行日期：  2018 年 6 月 22 日</span><span class="sxs-lookup"><span data-stu-id="041b1-335">*Release date: June 22, 2018*</span></span>

<span data-ttu-id="041b1-336">此版本包含多项社区贡献，并改进了调试体验，提高了性能。</span><span class="sxs-lookup"><span data-stu-id="041b1-336">This release includes several community contributions as well as an improved debugging experience and improved performance.</span></span>  <span data-ttu-id="041b1-337">具体而言：</span><span class="sxs-lookup"><span data-stu-id="041b1-337">Specifically:</span></span>

* <span data-ttu-id="041b1-338">对 QuantumSimulator 目标计算机的小型和大型模拟进行性能改进。</span><span class="sxs-lookup"><span data-stu-id="041b1-338">Performance improvements on both small and large simulations for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="041b1-339">改进了调试功能。</span><span class="sxs-lookup"><span data-stu-id="041b1-339">Improved debugging functionality.</span></span>
* <span data-ttu-id="041b1-340">在 bug 修复、新的帮助程序函数、操作和新示例方面的社区贡献。</span><span class="sxs-lookup"><span data-stu-id="041b1-340">Community contributions in bug fixes, new helper functions, operations and new samples.</span></span>

### <a name="performance-improvements"></a><span data-ttu-id="041b1-341">性能提升</span><span class="sxs-lookup"><span data-stu-id="041b1-341">Performance improvements</span></span>

<span data-ttu-id="041b1-342">此更新包括对所有目标计算机的大量和少量量子位模拟的显著性能改进。</span><span class="sxs-lookup"><span data-stu-id="041b1-342">This update includes significant performance improvements for simulation of large and small numbers of qubits for all the target machines.</span></span>  <span data-ttu-id="041b1-343">这种改进在量子开发工具包中的标准示例 H<sub>2</sub> 模拟中非常明显。</span><span class="sxs-lookup"><span data-stu-id="041b1-343">This improvement is easily visible with the H<sub>2</sub> simulation that is a standard sample in the Quantum Development Kit.</span></span>

### <a name="improved-debugging-functionality"></a><span data-ttu-id="041b1-344">改进了调试功能</span><span class="sxs-lookup"><span data-stu-id="041b1-344">Improved debugging functionality</span></span>

<span data-ttu-id="041b1-345">此更新添加了新的调试功能：</span><span class="sxs-lookup"><span data-stu-id="041b1-345">This update adds new debugging functionality:</span></span>
* <span data-ttu-id="041b1-346">添加了 @"microsoft.quantum.extensions.diagnostics.dumpmachine" 和 @"microsoft.quantum.extensions.diagnostics.dumpregister" 两个新操作，可在某个时间点输出有关目标量子计算机的波形函数信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-346">Added two new operations,  @"microsoft.quantum.extensions.diagnostics.dumpmachine" and @"microsoft.quantum.extensions.diagnostics.dumpregister" that output wave function information about the target quantum machine at a point in time.</span></span>  
* <span data-ttu-id="041b1-347">在 Visual Studio 中，在单个量子位测量到 $\ket{1}$ 的概率现在会自动显示在 QuantumSimulator 目标计算机的调试窗口中。</span><span class="sxs-lookup"><span data-stu-id="041b1-347">In Visual Studio, the probability of measuring a $\ket{1}$ on a single qubit is now automatically shown in the debugging window for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="041b1-348">在 Visual Studio 中，改进了“自动”和“局部变量”调试窗口中变量属性的显示   。</span><span class="sxs-lookup"><span data-stu-id="041b1-348">In Visual Studio, improved the display of variable properties in the **Autos** and **Locals** debug windows.</span></span> 

<span data-ttu-id="041b1-349">了解有关[测试和调试](xref:microsoft.quantum.techniques.testing-and-debugging)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-349">Learn more about [Testing and Debugging](xref:microsoft.quantum.techniques.testing-and-debugging).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="041b1-350">社区贡献</span><span class="sxs-lookup"><span data-stu-id="041b1-350">Community Contributions</span></span>

<span data-ttu-id="041b1-351">Q# 编码员社区正在不断发展，我们非常兴奋地看到第一个用户提供的库和示例已提交到 http://github.com/Microsoft/quantum 的开放代码库中。</span><span class="sxs-lookup"><span data-stu-id="041b1-351">The Q# coder community is growing and we are thrilled to see the first user contributed libraries and samples that were submitted to our open code base at http://github.com/Microsoft/quantum.</span></span>  <span data-ttu-id="041b1-352">非常感谢  ！</span><span class="sxs-lookup"><span data-stu-id="041b1-352">**A big Thank you!**</span></span> <span data-ttu-id="041b1-353">感谢以下参与者：</span><span class="sxs-lookup"><span data-stu-id="041b1-353">to the following contributors:</span></span>
* <span data-ttu-id="041b1-354">Mathias Soeken ([@msoeken](https://github.com/msoeken))：提供了一个定义基于转换的逻辑合成方法的示例，该方法可构造用于实现给定排列的 Toffoli 网络。</span><span class="sxs-lookup"><span data-stu-id="041b1-354">Mathias Soeken ([@msoeken](https://github.com/msoeken)):  contributed a sample defining a transformation based logic synthesis method that constructs Toffoli networks to implement a given permutation.</span></span> <span data-ttu-id="041b1-355">代码完全使用 Q# 函数和操作编写。</span><span class="sxs-lookup"><span data-stu-id="041b1-355">The code is written entirely in Q# functions and operations.</span></span>  <span data-ttu-id="041b1-356">[PR #41](https://github.com/Microsoft/Quantum/pull/41)。</span><span class="sxs-lookup"><span data-stu-id="041b1-356">[PR #41](https://github.com/Microsoft/Quantum/pull/41).</span></span>
* <span data-ttu-id="041b1-357">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman))：Microsoft MVP Rolf Huisman 提供了一个从 Q# 代码生成平面 QASM 代码的示例，用于不具有典型控制流的有限程序类和有限量子操作。</span><span class="sxs-lookup"><span data-stu-id="041b1-357">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)): Microsoft MVP Rolf Huisman contributed a sample that generates flat QASM code from Q# code for a restricted class of programs that do not have classical control flow and restricted quantum operations.</span></span> [<span data-ttu-id="041b1-358">PR #59</span><span class="sxs-lookup"><span data-stu-id="041b1-358">PR #59</span></span>](https://github.com/Microsoft/Quantum/pull/59)
* <span data-ttu-id="041b1-359">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314))：通过提交用于受控操作的库函数，帮助改进我们的代码库。</span><span class="sxs-lookup"><span data-stu-id="041b1-359">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): helped to improve our code base by submitting a library function for controlled operations.</span></span> [<span data-ttu-id="041b1-360">PR #53</span><span class="sxs-lookup"><span data-stu-id="041b1-360">PR #53</span></span>](https://github.com/Microsoft/Quantum/pull/53)
* <span data-ttu-id="041b1-361">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111))：修复 @"microsoft.quantum.canon.quantumphaseestimation" 并新建单元测试。</span><span class="sxs-lookup"><span data-stu-id="041b1-361">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): fixed @"microsoft.quantum.canon.quantumphaseestimation" and created new unit tests.</span></span>  [<span data-ttu-id="041b1-362">PR #54</span><span class="sxs-lookup"><span data-stu-id="041b1-362">PR #54</span></span>](https://github.com/Microsoft/Quantum/pull/54)
* <span data-ttu-id="041b1-363">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit))：通过确保释放 QuantumSimulator 实例来清除 Teleportation 示例。</span><span class="sxs-lookup"><span data-stu-id="041b1-363">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): cleaned the Teleportation sample by making sure the QuantumSimulator instance is disposed.</span></span> [<span data-ttu-id="041b1-364">PR #20</span><span class="sxs-lookup"><span data-stu-id="041b1-364">PR #20</span></span>](https://github.com/Microsoft/Quantum/pull/20)

<span data-ttu-id="041b1-365">此外，非常感谢你们  ：</span><span class="sxs-lookup"><span data-stu-id="041b1-365">Additionally, a big **Thank You!**</span></span> <span data-ttu-id="041b1-366">来自商业工程服务团队的 Microsoft 软件工程师参与者，他们在黑客马拉松期间对文档进行了重要的更改。</span><span class="sxs-lookup"><span data-stu-id="041b1-366">to these Microsoft Software Engineers from the Commercial Engineering Services team contributors who made valuable changes to our documentation during their Hackathon.</span></span>  <span data-ttu-id="041b1-367">他们作出的更改大大改善了我们所有人的清晰度和载入体验：</span><span class="sxs-lookup"><span data-stu-id="041b1-367">Their changes vastly improved the clarity and onboarding experience for all of us:</span></span>
* <span data-ttu-id="041b1-368">Sascha Corti</span><span class="sxs-lookup"><span data-stu-id="041b1-368">Sascha Corti</span></span>
* <span data-ttu-id="041b1-369">Mihaela Curmei</span><span class="sxs-lookup"><span data-stu-id="041b1-369">Mihaela Curmei</span></span>
* <span data-ttu-id="041b1-370">John Donnelly</span><span class="sxs-lookup"><span data-stu-id="041b1-370">John Donnelly</span></span>
* <span data-ttu-id="041b1-371">Kirill Logachev</span><span class="sxs-lookup"><span data-stu-id="041b1-371">Kirill Logachev</span></span>
* <span data-ttu-id="041b1-372">Jan Pospisil</span><span class="sxs-lookup"><span data-stu-id="041b1-372">Jan Pospisil</span></span>
* <span data-ttu-id="041b1-373">Anita Ramanan</span><span class="sxs-lookup"><span data-stu-id="041b1-373">Anita Ramanan</span></span>
* <span data-ttu-id="041b1-374">Frances Tibble</span><span class="sxs-lookup"><span data-stu-id="041b1-374">Frances Tibble</span></span>
* <span data-ttu-id="041b1-375">Alessandro Vozza</span><span class="sxs-lookup"><span data-stu-id="041b1-375">Alessandro Vozza</span></span>

### <a name="update-existing-projects"></a><span data-ttu-id="041b1-376">更新现有项目</span><span class="sxs-lookup"><span data-stu-id="041b1-376">Update existing projects</span></span>

<span data-ttu-id="041b1-377">此版本可完全向后兼容。</span><span class="sxs-lookup"><span data-stu-id="041b1-377">This release is fully backwards compatible.</span></span> <span data-ttu-id="041b1-378">只需将项目中的 nuget 包更新为 `0.2.1806.1503-preview` 版本，并执行全部重新生成，即可确保重新生成所有中间文件  。</span><span class="sxs-lookup"><span data-stu-id="041b1-378">Just update the nuget pakages in your projects to version `0.2.1806.1503-preview` and do a **full rebuild** to make sure all intermediate files are regenerated.</span></span>

<span data-ttu-id="041b1-379">在 Visual Studio 中，按照有关如何[更新包](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package)的常规说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="041b1-379">From Visual Studio, follow the normal instructions on how to [update a package](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).</span></span>

<span data-ttu-id="041b1-380">若要更新命令行的项目模板，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="041b1-380">To update project templates for the command line, run the following command:</span></span>
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

<span data-ttu-id="041b1-381">运行此命令后，使用 `dotnet new <project-type> -lang Q#` 创建的任何新项目将自动使用此版本的量子开发工具包。</span><span class="sxs-lookup"><span data-stu-id="041b1-381">After running this command, any new projects created using `dotnet new <project-type> -lang Q#` will automatically use this version of the Quantum Development Kit.</span></span>

<span data-ttu-id="041b1-382">若要更新现有项目以使用最新版本，请从每个项目的目录中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="041b1-382">To update an existing project to use the newest version, run the following command from within the directory for each project:</span></span>

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

<span data-ttu-id="041b1-383">如果现有项目还使用 XUnit 集成进行单元测试，则也可使用类似的命令来更新该包：</span><span class="sxs-lookup"><span data-stu-id="041b1-383">If an existing project also uses XUnit integration for unit testing, then a similar command can be used to update that package as well:</span></span>
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

<span data-ttu-id="041b1-384">根据测试项目所使用的 XUnit 版本，可能还需要将 XUnit 更新到 2.3.1：</span><span class="sxs-lookup"><span data-stu-id="041b1-384">Depending on the version of XUnit that your test project uses, you may also need to update XUnit to 2.3.1:</span></span>
```
dotnet add package xunit -v "2.3.1" 
```

<span data-ttu-id="041b1-385">更新后，请确保通过以下方式删除先前版本生成的所有临时文件：</span><span class="sxs-lookup"><span data-stu-id="041b1-385">After the update, make sure you remove all temporary files generated by the previous version by doing:</span></span>
```
dotnet clean 
```

### <a name="known-issues"></a><span data-ttu-id="041b1-386">已知问题</span><span class="sxs-lookup"><span data-stu-id="041b1-386">Known Issues</span></span>

<span data-ttu-id="041b1-387">未报告任何其他已知问题。</span><span class="sxs-lookup"><span data-stu-id="041b1-387">No aditional known issues to report.</span></span>


## <a name="version-0218022202"></a><span data-ttu-id="041b1-388">版本 0.2.1802.2202</span><span class="sxs-lookup"><span data-stu-id="041b1-388">Version 0.2.1802.2202</span></span>

<span data-ttu-id="041b1-389">发行日期：  2018 年 2 月 26 日</span><span class="sxs-lookup"><span data-stu-id="041b1-389">*Release date: February 26, 2018*</span></span>

<span data-ttu-id="041b1-390">此版本支持在多个平台上开发、语言互操作和性能增强。</span><span class="sxs-lookup"><span data-stu-id="041b1-390">This release brings support for development on more platforms, language interoperability, and performance enhancements.</span></span> <span data-ttu-id="041b1-391">具体而言：</span><span class="sxs-lookup"><span data-stu-id="041b1-391">Specifically:</span></span>

- <span data-ttu-id="041b1-392">支持基于 macOS 和 Linux 的开发。</span><span class="sxs-lookup"><span data-stu-id="041b1-392">Support for macOS- and Linux-based development.</span></span> 
- <span data-ttu-id="041b1-393">兼容 .NET Core，包括支持跨平台的 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="041b1-393">.NET Core compatibility, including support for Visual Studio Code across platforms.</span></span>
- <span data-ttu-id="041b1-394">量子开发工具包库的完整开放源代码许可证。</span><span class="sxs-lookup"><span data-stu-id="041b1-394">A full Open Source license for the Quantum Development Kit Libraries.</span></span>
- <span data-ttu-id="041b1-395">提高了需要 20 个或以上量子位的项目的模拟器性能。</span><span class="sxs-lookup"><span data-stu-id="041b1-395">Improved simulator performance on projects requiring 20 or more qubits.</span></span>
- <span data-ttu-id="041b1-396">可与 Python 语言（适用于 Windows 的预览版本）互操作。</span><span class="sxs-lookup"><span data-stu-id="041b1-396">Interoperability with the Python language (preview release available on Windows).</span></span>

### <a name="net-editions"></a><span data-ttu-id="041b1-397">.NET 版本</span><span class="sxs-lookup"><span data-stu-id="041b1-397">.NET Editions</span></span>

<span data-ttu-id="041b1-398">.NET 平台具有两种不同的版本：随 Windows 提供的 .NET Framework，以及在 Windows、macOS 和 Linux 上提供的开源 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="041b1-398">The .NET platform is available through two different editions, the .NET Framework that is provided with Windows, and the open-source .NET Core that is available on Windows, macOS and Linux.</span></span>
<span data-ttu-id="041b1-399">在此版本中，量子开发工具包的大部分内容作为 .NET Standard 的库提供，该库是 Framework 和 Core 共用的一组类。</span><span class="sxs-lookup"><span data-stu-id="041b1-399">With this release, most parts of the Quantum Development Kit are provided as libraries for .NET Standard, the set of classes common to both Framework and Core.</span></span>
<span data-ttu-id="041b1-400">这些库因此与 .NET Framework 或 .NET Core 的最新版本兼容。</span><span class="sxs-lookup"><span data-stu-id="041b1-400">These libraries are therefore compatible with recent versions of either .NET Framework or .NET Core.</span></span>

<span data-ttu-id="041b1-401">因此，为了帮助确保使用量子开发工具包编写的项目尽可能成为可移植项目，我们建议使用量子开发工具包编写的库项目面向 .NET Standard，而控制台应用程序面向 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="041b1-401">Thus, to help ensure that projects written using the Quantum Development Kit are as portable as possible, we recommend that library projects written using the Quantum Development Kit target .NET Standard, while console applications target .NET Core.</span></span>
<span data-ttu-id="041b1-402">由于以前版本的量子开发工具包仅支持 .NET Framework，因此可能需要迁移现有项目；有关如何执行此操作的详细信息，请参阅以下内容。</span><span class="sxs-lookup"><span data-stu-id="041b1-402">Since previous releases of the Quantum Development Kit only supported .NET Framework, you may need to migrate your existing projects; see below for details on how to do this.</span></span>

### <a name="project-migration"></a><span data-ttu-id="041b1-403">项目迁移</span><span class="sxs-lookup"><span data-stu-id="041b1-403">Project Migration</span></span>

<span data-ttu-id="041b1-404">只要未更新使用较低版本的量子开发工具包创建的项目中所用的 NuGet 包，则该项目仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="041b1-404">Projects created using previous versions of Quantum Development Kit will still work, as long as you don't update the NuGet packages used in them.</span></span> <span data-ttu-id="041b1-405">若要将现有代码迁移到新版本，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="041b1-405">To migrate existing code to the new version, perform the following steps:</span></span>
1. <span data-ttu-id="041b1-406">使用合适类型的 Q# 项目模板（应用程序、库或测试项目）创建新的 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="041b1-406">Create a new .NET Core project using the right type of Q# project template (Application, Library or Test Project).</span></span>
2. <span data-ttu-id="041b1-407">将旧项目中的现有 .qs 和 .cs/.fs 文件复制到新项目（使用“添加”>“现有项”）。</span><span class="sxs-lookup"><span data-stu-id="041b1-407">Copy existing .qs and .cs/.fs files from the old project to the new project (using Add > Existing Item).</span></span> <span data-ttu-id="041b1-408">请勿复制 AssemblyInfo.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="041b1-408">Do not copy the AssemblyInfo.cs file.</span></span>
3. <span data-ttu-id="041b1-409">生成并运行新项目。</span><span class="sxs-lookup"><span data-stu-id="041b1-409">Build and run the new project.</span></span>

<span data-ttu-id="041b1-410">请注意，Microsoft.Quantum.Canon 命名空间的 RandomWalkPhaseEstimation 操作已移动到 [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) 存储库中的 Microsoft.Research.Quantum.RandomWalkPhaseEstimation 命名空间。</span><span class="sxs-lookup"><span data-stu-id="041b1-410">Please note that the operation RandomWalkPhaseEstimation from the namespace Microsoft.Quantum.Canon was moved into the namespace Microsoft.Research.Quantum.RandomWalkPhaseEstimation in the [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) repository.</span></span>

### <a name="known-issues"></a><span data-ttu-id="041b1-411">已知问题</span><span class="sxs-lookup"><span data-stu-id="041b1-411">Known Issues</span></span>

- <span data-ttu-id="041b1-412">`dotnet test` 的 `--filter` 选项无法正常用于使用 Q# 编写的测试。</span><span class="sxs-lookup"><span data-stu-id="041b1-412">The `--filter` option to `dotnet test` does not work correctly for tests written in Q#.</span></span>
  <span data-ttu-id="041b1-413">因此，无法在 Visual Studio Code 中运行单个单元测试；建议在命令行中使用 `dotnet test` 重新运行所有测试。</span><span class="sxs-lookup"><span data-stu-id="041b1-413">As a result, individual unit tests cannot be run in Visual Studio Code; we recommend using `dotnet test` at the command line to re-run all tests.</span></span>

## <a name="version-0118011707"></a><span data-ttu-id="041b1-414">版本 0.1.1801.1707</span><span class="sxs-lookup"><span data-stu-id="041b1-414">Version 0.1.1801.1707</span></span>

<span data-ttu-id="041b1-415">发行日期：  2018 年 1 月 18 日</span><span class="sxs-lookup"><span data-stu-id="041b1-415">*Release date: January 18, 2018*</span></span>

<span data-ttu-id="041b1-416">此版本修复了社区报告的一些问题。</span><span class="sxs-lookup"><span data-stu-id="041b1-416">This release fixes some issues reported by the community.</span></span> <span data-ttu-id="041b1-417">也就是说，</span><span class="sxs-lookup"><span data-stu-id="041b1-417">Namely:</span></span>

- <span data-ttu-id="041b1-418">模拟器现适用于不支持 AVX 的早期 CPU。</span><span class="sxs-lookup"><span data-stu-id="041b1-418">The simulator now works with early non-AVX-enabled CPUs.</span></span>
- <span data-ttu-id="041b1-419">区域十进制设置不会导致 Q# 分析器发生故障。</span><span class="sxs-lookup"><span data-stu-id="041b1-419">Regional decimal settings will not cause the Q# parser to fail.</span></span>
- <span data-ttu-id="041b1-420">`SignD` 基元操作现返回 `Int`，而不是 `Double`。</span><span class="sxs-lookup"><span data-stu-id="041b1-420">`SignD` primitive operation now returns `Int` rather than `Double`.</span></span>


## <a name="version-011712901"></a><span data-ttu-id="041b1-421">版本 0.1.1712.901</span><span class="sxs-lookup"><span data-stu-id="041b1-421">Version 0.1.1712.901</span></span>

<span data-ttu-id="041b1-422">发行日期：  2017 年 12 月 11 日</span><span class="sxs-lookup"><span data-stu-id="041b1-422">*Release date: December 11, 2017*</span></span>

### <a name="known-issues"></a><span data-ttu-id="041b1-423">已知问题</span><span class="sxs-lookup"><span data-stu-id="041b1-423">Known Issues</span></span>

#### <a name="hardware-and-software-requirements"></a><span data-ttu-id="041b1-424">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="041b1-424">Hardware and Software Requirements</span></span>

- <span data-ttu-id="041b1-425">量子开发工具包随附的模拟器需要安装 64 位的 Microsoft Windows 才能运行。</span><span class="sxs-lookup"><span data-stu-id="041b1-425">The simulator included with the Quantum Development Kit requires a 64-bit installation of Microsoft Windows to run.</span></span>
- <span data-ttu-id="041b1-426">Microsoft 的量子模拟器与量子开发工具包一起安装，利用高级矢量扩展 (AVX)，并且需要支持 AVX 的 CPU。</span><span class="sxs-lookup"><span data-stu-id="041b1-426">Microsoft's quantum simulator, installed with the Quantum Development Kit, utilizes Advance Vector Extensions (AVX), and requires an AVX-enabled CPU.</span></span> <span data-ttu-id="041b1-427">2011 年 1 季度 (Sandy Bridge) 或之后推出的 Intel 处理器支持 AVX。</span><span class="sxs-lookup"><span data-stu-id="041b1-427">Intel processors shipped in Q1 2011 (Sandy Bridge) or later support AVX.</span></span> <span data-ttu-id="041b1-428">我们正在评估对早期 CPU 的支持，稍后会公布详细信息。</span><span class="sxs-lookup"><span data-stu-id="041b1-428">We are evaluating support for earlier CPUs and may announce details at a later time.</span></span>

#### <a name="project-creation"></a><span data-ttu-id="041b1-429">项目创建</span><span class="sxs-lookup"><span data-stu-id="041b1-429">Project Creation</span></span>

- <span data-ttu-id="041b1-430">创建将使用 Q# 的解决方案 (.sln) 时，解决方案所在的目录必须高于解决方案中每个项目 (.csproj)。</span><span class="sxs-lookup"><span data-stu-id="041b1-430">When creating a solution (.sln) that will use Q#, the solution must be one directory higher than each project (.csproj) in the solution.</span></span> <span data-ttu-id="041b1-431">若要新建解决方案，请确保选中“新建项目”对话框中的“创建解决方案的目录”复选框。</span><span class="sxs-lookup"><span data-stu-id="041b1-431">When creating a new solution, this can be accomplished by making sure that the "Create directory for solution" checkbox on the "New Project" dialog box is checked.</span></span> <span data-ttu-id="041b1-432">如果未能创建，则需要手动安装量子开发工具包 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="041b1-432">If this is not done, the Quantum Development Kit NuGet packages will need to be installed manually.</span></span>

#### <a name="q"></a><span data-ttu-id="041b1-433">Q#</span><span class="sxs-lookup"><span data-stu-id="041b1-433">Q#</span></span>

- <span data-ttu-id="041b1-434">Intellisense 不显示 Q# 代码的正确错误。</span><span class="sxs-lookup"><span data-stu-id="041b1-434">Intellisense does not display proper errors for Q# code.</span></span> <span data-ttu-id="041b1-435">请确保在 Visual Studio 错误列表中显示生成错误，以查看正确的 Q# 错误。</span><span class="sxs-lookup"><span data-stu-id="041b1-435">Make sure that you are displaying Build errors in the Visual Studio Error List to see correct Q# errors.</span></span> <span data-ttu-id="041b1-436">另请注意，在完成生成之前不会显示 Q# 错误。</span><span class="sxs-lookup"><span data-stu-id="041b1-436">Also note that Q# errors will not show up until after you've done a build.</span></span>
- <span data-ttu-id="041b1-437">在部分应用程序中使用可变数组可能导致意外的行为。</span><span class="sxs-lookup"><span data-stu-id="041b1-437">Using a mutable array in a partial application may lead to unexpected behavior.</span></span>
- <span data-ttu-id="041b1-438">将不可变数组绑定到可变数组（令 a = b，其中 b 是可变数组）可能会导致意外的行为。</span><span class="sxs-lookup"><span data-stu-id="041b1-438">Binding an immutable array to a mutable array (let a = b, where b is a mutable array) may lead to unexpected behavior.</span></span>
- <span data-ttu-id="041b1-439">分析、代码覆盖率和其他 VS 插件可能不会始终准确地统计 Q# 行和块。</span><span class="sxs-lookup"><span data-stu-id="041b1-439">Profiling, code coverage and other VS plugins may not always count Q# lines and blocks accurately.</span></span>
- <span data-ttu-id="041b1-440">Q# 编译器不会验证内插字符串。</span><span class="sxs-lookup"><span data-stu-id="041b1-440">The Q# compiler does not validate interpolated strings.</span></span> <span data-ttu-id="041b1-441">可以通过拼写错误的变量名或在 Q# 内插字符串中使用表达式，来创建 C# 编译错误。</span><span class="sxs-lookup"><span data-stu-id="041b1-441">It is possible to create C# compilation errors by misspelling variable names or using expressions in Q# interpolated strings.</span></span>

#### <a name="simulation"></a><span data-ttu-id="041b1-442">模拟</span><span class="sxs-lookup"><span data-stu-id="041b1-442">Simulation</span></span>

- <span data-ttu-id="041b1-443">量子模拟器使用 OpenMP 并行化所需的线性代数。</span><span class="sxs-lookup"><span data-stu-id="041b1-443">The Quantum Simulator uses OpenMP to parallelize the linear algebra required.</span></span> <span data-ttu-id="041b1-444">OpenMP 默认使用所有可用的硬件线程，这意味着具有少量的量子位的程序通常运行缓慢，因为所需的协调远多于实际工作。</span><span class="sxs-lookup"><span data-stu-id="041b1-444">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="041b1-445">通过将环境变量 OMP_NUM_THREADS 设置为较小数值，可修复此故障。</span><span class="sxs-lookup"><span data-stu-id="041b1-445">This can be fixed by setting the environment variable OMP_NUM_THREADS to a small number.</span></span> <span data-ttu-id="041b1-446">作为非常粗略的经验法则，1 个线程最多可以容纳约 4 个量子位，然后每个量子位最好增加一个线程，但这在很大程度上取决于你的算法。</span><span class="sxs-lookup"><span data-stu-id="041b1-446">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

#### <a name="debugging"></a><span data-ttu-id="041b1-447">调试</span><span class="sxs-lookup"><span data-stu-id="041b1-447">Debugging</span></span>

- <span data-ttu-id="041b1-448">F11（单步执行）在 Q# 代码中不起作用。</span><span class="sxs-lookup"><span data-stu-id="041b1-448">F11 (step in) doesn't work in Q# code.</span></span>
- <span data-ttu-id="041b1-449">在断点处暂停或单步暂停时，Q# 代码中的代码突出显示有时并不准确。</span><span class="sxs-lookup"><span data-stu-id="041b1-449">Code highlighting in Q# code at a breakpoint or single-step pause is sometimes inaccurate.</span></span> <span data-ttu-id="041b1-450">虽然系统会突出显示正确的行，但有时突出显示将从行中不正确的列开始和结束。</span><span class="sxs-lookup"><span data-stu-id="041b1-450">The correct line will be highlighted, but sometimes the highlight will start and end at incorrect columns on the line.</span></span>

#### <a name="testing"></a><span data-ttu-id="041b1-451">测试</span><span class="sxs-lookup"><span data-stu-id="041b1-451">Testing</span></span>

- <span data-ttu-id="041b1-452">必须在 64 位模式下执行测试。</span><span class="sxs-lookup"><span data-stu-id="041b1-452">Tests must be executed in 64-bit mode.</span></span> <span data-ttu-id="041b1-453">如果测试失败，并出现 BadImageFormatException，请转到“测试”菜单，依次选择“测试设置”>“默认处理器体系结构”>“X64”。</span><span class="sxs-lookup"><span data-stu-id="041b1-453">If your tests are failing with a BadImageFormatException, go to the Test menu and select Test Settings > Default Processor Architecture > X64.</span></span>
- <span data-ttu-id="041b1-454">有些测试需要很长的运行时间，可能需要 5 分钟，具体取决于你的计算机。</span><span class="sxs-lookup"><span data-stu-id="041b1-454">Some tests take a long time (possibly as much as 5 minutes depending on your computer) to run.</span></span> <span data-ttu-id="041b1-455">这是正常的，因为有些测试使用超过 20 个量子位；我们目前最大的测试可运行 23 个量子位。</span><span class="sxs-lookup"><span data-stu-id="041b1-455">This is normal, as some use over twenty qubits; our largest test currently runs on 23 qubits.</span></span>

#### <a name="samples"></a><span data-ttu-id="041b1-456">示例</span><span class="sxs-lookup"><span data-stu-id="041b1-456">Samples</span></span>

- <span data-ttu-id="041b1-457">在某些计算机上，除非将环境变量 OMP_NUM_THREADS 设置为“1”，否则一些小样本可能会运行缓慢。</span><span class="sxs-lookup"><span data-stu-id="041b1-457">On some machines, some small samples may run slowly unless the environment variable OMP_NUM_THREADS is set to "1".</span></span> <span data-ttu-id="041b1-458">另请参见“模拟”下的发行说明。</span><span class="sxs-lookup"><span data-stu-id="041b1-458">See also the release note under "Simulation".</span></span>

#### <a name="libraries"></a><span data-ttu-id="041b1-459">库</span><span class="sxs-lookup"><span data-stu-id="041b1-459">Libraries</span></span>

- <span data-ttu-id="041b1-460">有一个隐含的假设，即以不同的参数传递给操作的量子位都是不同的。</span><span class="sxs-lookup"><span data-stu-id="041b1-460">There is an implicit assumption that the qubits passed to an operation in different arguments are all distinct.</span></span> <span data-ttu-id="041b1-461">例如，所有库操作（和所有模拟器）都假定传递给受控 NOT 的两个量子位是不同的量子位。</span><span class="sxs-lookup"><span data-stu-id="041b1-461">For instance, all of the library operations (and all of the simulators) assume that the two qubits passed to a controlled NOT are different qubits.</span></span> <span data-ttu-id="041b1-462">违反此假设可能会导致发生无法预料的意外情况。</span><span class="sxs-lookup"><span data-stu-id="041b1-462">Violating this assumption may lead to unpredictable unexpected.</span></span> <span data-ttu-id="041b1-463">可以使用量子计算机跟踪器模拟器对此进行测试。</span><span class="sxs-lookup"><span data-stu-id="041b1-463">It is possible to test for this using the quantum computer tracer simulator.</span></span>
- <span data-ttu-id="041b1-464">Microsoft.Quantum.Bind 函数可能无法在所有情况下都按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="041b1-464">The Microsoft.Quantum.Bind function may not act as expected in all cases.</span></span>
- <span data-ttu-id="041b1-465">在 Microsoft.Quantum.Extensions.Math 命名空间中，尽管基础 System.Math.Sign 函数始终返回整数，但 SignD 函数返回 Double 类型而非 Int 类型。</span><span class="sxs-lookup"><span data-stu-id="041b1-465">In the Microsoft.Quantum.Extensions.Math namespace, the SignD function returns a Double rather than an Int, although the underlying System.Math.Sign function always returns an integer.</span></span> <span data-ttu-id="041b1-466">可以安全地将结果与 1.0、-1.0 和 0.0 进行比较，因为这些双精度值均具有精确的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="041b1-466">It is safe to compare the result against 1.0, -1.0, and 0.0, since these doubles all have exact binary representations.</span></span>