---
title: Quantum 开发工具包发行说明
description: 了解 Microsoft Quantum 开发工具包预览版的最新更新。
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: 70d0c9b61e49d4ee6142edbe2767310403885f01
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992252"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a><span data-ttu-id="e91b4-103">Microsoft 量子开发工具包发行说明</span><span class="sxs-lookup"><span data-stu-id="e91b4-103">Microsoft Quantum Development Kit Release Notes</span></span>

<span data-ttu-id="e91b4-104">本文包含有关每个量子开发工具包版本的信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-104">This article contains information on each Quantum Development Kit release.</span></span>

<span data-ttu-id="e91b4-105">有关安装说明，请参阅[安装指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-105">For installation instructions, please refer to the [install guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="e91b4-106">有关更新说明，请参阅[更新指南](xref:microsoft.quantum.update)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-106">For update instructions, please refer to the [update guide](xref:microsoft.quantum.update).</span></span>

## <a name="version-01220082513"></a><span data-ttu-id="e91b4-107">版本0.12.20082513</span><span class="sxs-lookup"><span data-stu-id="e91b4-107">Version 0.12.20082513</span></span>

<span data-ttu-id="e91b4-108">*发布日期：2020年8月25日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-108">*Release date: August 25th, 2020*</span></span>

<span data-ttu-id="e91b4-109">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-109">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-110">新的[Microsoft 量子命名空间](xref:microsoft.quantum.random)，提供更方便的方法来从程序内采样随机值。 Q#</span><span class="sxs-lookup"><span data-stu-id="e91b4-110">New [Microsoft.Quantum.Random namespace](xref:microsoft.quantum.random), providing a more convenient way to sample random values from within Q# programs.</span></span> <span data-ttu-id="e91b4-111"> ([QuantumLibraries # 311](https://github.com/microsoft/QuantumLibraries/pull/311)， [qsharp # 328](https://github.com/microsoft/qsharp-runtime/pull/328)) </span><span class="sxs-lookup"><span data-stu-id="e91b4-111">([QuantumLibraries#311](https://github.com/microsoft/QuantumLibraries/pull/311), [qsharp-runtime#328](https://github.com/microsoft/qsharp-runtime/pull/328))</span></span>
- <span data-ttu-id="e91b4-112">改进了带有新[ `DumpOperation` 操作](xref:microsoft.quantum.diagnostics.dumpoperation)的[Microsoft 量子命名空间](xref:microsoft.quantum.diagnostics)，以及用于限制 qubit 分配和 oracle 调用的新操作。</span><span class="sxs-lookup"><span data-stu-id="e91b4-112">Improved [Microsoft.Quantum.Diagnostics namespace](xref:microsoft.quantum.diagnostics) with new [`DumpOperation` operation](xref:microsoft.quantum.diagnostics.dumpoperation), and new operations for restricting qubit allocation and oracle calls.</span></span> <span data-ttu-id="e91b4-113"> ([QuantumLibraries # 302](https://github.com/microsoft/QuantumLibraries/pull/302)) </span><span class="sxs-lookup"><span data-stu-id="e91b4-113">([QuantumLibraries#302](https://github.com/microsoft/QuantumLibraries/pull/302))</span></span>
- <span data-ttu-id="e91b4-114">在[ `%project` ](xref:microsoft.quantum.iqsharp.magic-ref.project)我 Q# 和 Python 中的[ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects)中新建神奇命令，以支持对 Q# 当前工作区文件夹之外的项目的引用。</span><span class="sxs-lookup"><span data-stu-id="e91b4-114">New [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) in IQ# and [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) in Python to support references to Q# projects outside the current workspace folder.</span></span> <span data-ttu-id="e91b4-115">有关此功能的当前限制，请参阅 [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-115">See [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for the current limitations of this feature.</span></span> 
- <span data-ttu-id="e91b4-116">支持自动加载 `.csproj` I Q# /Python 主机的文件，这允许在初始化时加载外部项目或包引用。</span><span class="sxs-lookup"><span data-stu-id="e91b4-116">Support for automatically loading `.csproj` files for IQ#/Python hosts, which allows external project or package references to be loaded at initialization time.</span></span> <span data-ttu-id="e91b4-117">有关更多详细信息，请参阅使用[ Q# Python 和 Jupyter 笔记本](xref:microsoft.quantum.guide.host-programs)的指南。</span><span class="sxs-lookup"><span data-stu-id="e91b4-117">See the guide for using [Q# with Python and Jupyter Notebooks](xref:microsoft.quantum.guide.host-programs) for more details.</span></span>
- <span data-ttu-id="e91b4-118">添加了 ErrorCorrection 示例。</span><span class="sxs-lookup"><span data-stu-id="e91b4-118">Added ErrorCorrection.Syndrome sample.</span></span>
- <span data-ttu-id="e91b4-119">向 SimpleIsing 添加了可调式耦合。</span><span class="sxs-lookup"><span data-stu-id="e91b4-119">Added tunable coupling to SimpleIsing.</span></span>
- <span data-ttu-id="e91b4-120">更新了 HiddenShift 示例。</span><span class="sxs-lookup"><span data-stu-id="e91b4-120">Updated HiddenShift sample.</span></span>
- <span data-ttu-id="e91b4-121">添加了用于通过 Grover 的算法求解 Sudoku 的示例 (外部贡献) </span><span class="sxs-lookup"><span data-stu-id="e91b4-121">Added sample for solving Sudoku with Grover's algorithm (external contribution)</span></span>
- <span data-ttu-id="e91b4-122">一般 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="e91b4-122">General bug fixes.</span></span>

<span data-ttu-id="e91b4-123">请参阅适用于[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的已关闭 pr 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-123">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01220072031"></a><span data-ttu-id="e91b4-124">版本0.12.20072031</span><span class="sxs-lookup"><span data-stu-id="e91b4-124">Version 0.12.20072031</span></span>

<span data-ttu-id="e91b4-125">*发布日期：2020年7月21日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-125">*Release date: July 21st, 2020*</span></span>

<span data-ttu-id="e91b4-126">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-126">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-127">笔记本中打开 Q# 的命名空间现可用于以后的所有单元执行。</span><span class="sxs-lookup"><span data-stu-id="e91b4-127">Opened namespaces in Q# notebooks are now available for all future cell executions.</span></span> <span data-ttu-id="e91b4-128">例如，这样就可以在笔记本顶部的单元中打开一次命名空间，而无需在每个代码单元格中打开相关的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e91b4-128">This allows, for example, namespaces to be opened once in a cell at the top of the notebook, rather than needing to open relevant namespaces in each code cell.</span></span> <span data-ttu-id="e91b4-129">新的 `%lsopen` 幻命令显示当前打开的命名空间的列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-129">A new `%lsopen` magic command displays the list of currently-opened namespaces.</span></span>

<span data-ttu-id="e91b4-130">请参阅适用于[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的已关闭 pr 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-130">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01220070124"></a><span data-ttu-id="e91b4-131">版本0.12.20070124</span><span class="sxs-lookup"><span data-stu-id="e91b4-131">Version 0.12.20070124</span></span>

<span data-ttu-id="e91b4-132">*发布日期：2020年7月2日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-132">*Release date: July 2nd, 2020*</span></span>

<span data-ttu-id="e91b4-133">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-133">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-134">`qdk-chem`用于转换旧电子结构问题序列化格式的新工具 (例如： FCIDUMP) 到[Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)</span><span class="sxs-lookup"><span data-stu-id="e91b4-134">New `qdk-chem` tool for converting legacy electronic structure problem serialization formats (e.g.: FCIDUMP) to [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)</span></span>
- <span data-ttu-id="e91b4-135">一致命名空间中的新函数和操作 [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) 使用基于转换和分解的合成算法来应用传统 oracles。</span><span class="sxs-lookup"><span data-stu-id="e91b4-135">New functions and operations in the [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) namespace for coherently applying classical oracles using transformation- and decomposition-based synthesis algorithms.</span></span>
- <span data-ttu-id="e91b4-136">我 Q# 现在允许将参数用于 `%simulate` 、 `%estimate` 和其他幻命令。</span><span class="sxs-lookup"><span data-stu-id="e91b4-136">IQ# now allows arguments to the `%simulate`, `%estimate`, and other magic commands.</span></span> <span data-ttu-id="e91b4-137">有关更多详细信息，请参阅[ `%simulate` 幻命令参考](xref:microsoft.quantum.iqsharp.magic-ref.simulate)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-137">See the [`%simulate` magic command reference](xref:microsoft.quantum.iqsharp.magic-ref.simulate) for more details.</span></span>
- <span data-ttu-id="e91b4-138">I 中的新阶段显示选项 Q# 。有关更多详细信息，请参阅[ `%config` 幻命令参考](xref:microsoft.quantum.iqsharp.magic-ref.config)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-138">New phase display options in IQ#. See the [`%config` magic command reference](xref:microsoft.quantum.iqsharp.magic-ref.config) for more details.</span></span>
- <span data-ttu-id="e91b4-139">Q#现在，我和 `qsharp` Python 包都是通过 conda 包提供 ([qsharp](https://anaconda.org/quantum-engineering/qsharp)和[iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) 来简化 Q# Jupyter 和 Python 功能到 conda 环境的本地安装。</span><span class="sxs-lookup"><span data-stu-id="e91b4-139">IQ# and the `qsharp` Python package are now provided via conda packages ([qsharp](https://anaconda.org/quantum-engineering/qsharp) and [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) to simplify local installation of Q# Jupyter and Python functionality to a conda environment.</span></span> <span data-ttu-id="e91b4-140">有关更多详细信息，请参阅[ Q# Jupyter 笔记本](xref:microsoft.quantum.install.jupyter)和[ Q# Python](xref:microsoft.quantum.install.python)安装指南。</span><span class="sxs-lookup"><span data-stu-id="e91b4-140">See the [Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) and [Q# with Python](xref:microsoft.quantum.install.python) installation guides for more details.</span></span>
- <span data-ttu-id="e91b4-141">使用模拟器时，qubits 不再需要处于版本 | 0 ⟩状态，如果在释放前立即测量，则可以自动重置。</span><span class="sxs-lookup"><span data-stu-id="e91b4-141">When using the simulator, qubits no longer need to be in the |0⟩ state upon release, but can be automatically reset if they were measured immediately before releasing.</span></span>
- <span data-ttu-id="e91b4-142">用于使用户更轻松地 Q# 使用具有不同 QDK 版本的库包的更新，只需要主要 & 次版本号匹配，而不是完全相同的版本</span><span class="sxs-lookup"><span data-stu-id="e91b4-142">Updates to make it easier for IQ# users to consume library packages with different QDK versions, requiring only major & minor version numbers match rather than the exact same version</span></span>
- <span data-ttu-id="e91b4-143">删除不推荐使用的 `Microsoft.Quantum.Primitive.*` 命名空间</span><span class="sxs-lookup"><span data-stu-id="e91b4-143">Removed deprecated `Microsoft.Quantum.Primitive.*` namespace</span></span>
- <span data-ttu-id="e91b4-144">移动操作：</span><span class="sxs-lookup"><span data-stu-id="e91b4-144">Moved operations:</span></span>
  - <span data-ttu-id="e91b4-145">`Microsoft.Quantum.Intrinsic.Assert` 现为 `Microsoft.Quantum.Diagnostics.AssertMeasurement`</span><span class="sxs-lookup"><span data-stu-id="e91b4-145">`Microsoft.Quantum.Intrinsic.Assert` is now `Microsoft.Quantum.Diagnostics.AssertMeasurement`</span></span>
  - <span data-ttu-id="e91b4-146">`Microsoft.Quantum.Intrinsic.AssertProb` 现为 `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`</span><span class="sxs-lookup"><span data-stu-id="e91b4-146">`Microsoft.Quantum.Intrinsic.AssertProb` is now `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`</span></span>
- <span data-ttu-id="e91b4-147">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="e91b4-147">Bug fixes</span></span> 

<span data-ttu-id="e91b4-148">请参阅适用于[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的已关闭 pr 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-148">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-0112006403"></a><span data-ttu-id="e91b4-149">版本 0.11.2006.403</span><span class="sxs-lookup"><span data-stu-id="e91b4-149">Version 0.11.2006.403</span></span>

<span data-ttu-id="e91b4-150">发行日期：*2020 年 6 月 4 日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-150">*Release date: June 4th, 2020*</span></span>

<span data-ttu-id="e91b4-151">此版本修复了影响项目编译的 bug Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-151">This release fixes a bug affecting compilation of Q# projects.</span></span>

## <a name="version-0112006207"></a><span data-ttu-id="e91b4-152">版本 0.11.2006.207</span><span class="sxs-lookup"><span data-stu-id="e91b4-152">Version 0.11.2006.207</span></span>

<span data-ttu-id="e91b4-153">发行日期：*2020 年 6 月 3 日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-153">*Release date: June 3rd, 2020*</span></span>

<span data-ttu-id="e91b4-154">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-154">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-155">Q#存在入口点时，笔记本和 Python 主机程序将不再失败 Q#</span><span class="sxs-lookup"><span data-stu-id="e91b4-155">Q# notebooks and Python host programs will no longer fail when a Q# entry point is present</span></span>
- <span data-ttu-id="e91b4-156">更新了[标准库](xref:microsoft.quantum.libraries.standard.intro)以使用访问修饰符</span><span class="sxs-lookup"><span data-stu-id="e91b4-156">Updates to [Standard library](xref:microsoft.quantum.libraries.standard.intro) to use access modifiers</span></span>
- <span data-ttu-id="e91b4-157">编译器现在允许在内置重写步骤之间插入重写步骤</span><span class="sxs-lookup"><span data-stu-id="e91b4-157">Compiler now allows plug-in of rewrite steps between built-in rewrite steps</span></span>
- <span data-ttu-id="e91b4-158">按照 [API 原则](xref:microsoft.quantum.contributing.api-design)中所述的计划删除了几个弃用的函数和操作。</span><span class="sxs-lookup"><span data-stu-id="e91b4-158">Several deprecated functions and operations have been removed following the schedule described in our [API principles](xref:microsoft.quantum.contributing.api-design).</span></span> <span data-ttu-id="e91b4-159">Q# 在版本0.11.2004.2825 中生成但未出现警告的程序和库将继续工作。</span><span class="sxs-lookup"><span data-stu-id="e91b4-159">Q# programs and libraries that build without warnings in version 0.11.2004.2825 will continue to work unmodified.</span></span>

<span data-ttu-id="e91b4-160">请参阅适用于[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的已关闭 pr 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-160">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

> [!NOTE]
> <span data-ttu-id="e91b4-161">此版本包含影响项目编译的 bug Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-161">This version contains a bug affecting compilation of Q# projects.</span></span> <span data-ttu-id="e91b4-162">建议升级到较新版本。</span><span class="sxs-lookup"><span data-stu-id="e91b4-162">We recommend upgrading to a newer release.</span></span>

## <a name="version-01120042825"></a><span data-ttu-id="e91b4-163">版本 0.11.2004.2825</span><span class="sxs-lookup"><span data-stu-id="e91b4-163">Version 0.11.2004.2825</span></span>

<span data-ttu-id="e91b4-164">发行日期：*2020 年 4 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-164">*Release date: April 30th, 2020*</span></span>

<span data-ttu-id="e91b4-165">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-165">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-166">新的对 Q# 应用程序的支持，不再需要 c # 或 Python 主机文件。</span><span class="sxs-lookup"><span data-stu-id="e91b4-166">New support for Q# applications, which no longer require a C# or Python host file.</span></span> <span data-ttu-id="e91b4-167">有关应用程序入门的详细信息 Q# ，请参阅 [此处](xref:microsoft.quantum.install.standalone)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-167">For more information on getting started with Q# applications, see [here](xref:microsoft.quantum.install.standalone).</span></span>
- <span data-ttu-id="e91b4-168">更新了量子随机数生成器快速入门，从而不再需要 C# 或 Python 主机文件。</span><span class="sxs-lookup"><span data-stu-id="e91b4-168">Updated quantum random number generator quickstart to no longer require a C# or Python host file.</span></span> <span data-ttu-id="e91b4-169">参阅更新的[快速入门](xref:microsoft.quantum.quickstarts.qrng)</span><span class="sxs-lookup"><span data-stu-id="e91b4-169">See the updated  [Quickstart](xref:microsoft.quantum.quickstarts.qrng)</span></span>
- <span data-ttu-id="e91b4-170">对我的 Docker 映像的性能改进 Q#</span><span class="sxs-lookup"><span data-stu-id="e91b4-170">Performance improvements to IQ# Docker images</span></span>

> [!NOTE]
> <span data-ttu-id="e91b4-171">Q#[`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint)当前无法从 Python 或 .net 主机程序调用使用新属性的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e91b4-171">Q# applications using the new [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) attribute currently cannot be called from Python or .NET host programs.</span></span>
> <span data-ttu-id="e91b4-172">有关详细信息，请参阅 [Python](xref:microsoft.quantum.install.python) 和 [.NET 互操作性](xref:microsoft.quantum.install.cs)指南。</span><span class="sxs-lookup"><span data-stu-id="e91b4-172">See the [Python](xref:microsoft.quantum.install.python) and [.NET interoperability](xref:microsoft.quantum.install.cs) guides for more information.</span></span>

## <a name="version-01120033107"></a><span data-ttu-id="e91b4-173">版本 0.11.2003.3107</span><span class="sxs-lookup"><span data-stu-id="e91b4-173">Version 0.11.2003.3107</span></span>

<span data-ttu-id="e91b4-174">发行日期：*2020 年 3 月 31 日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-174">*Release date: March 31, 2020*</span></span>

<span data-ttu-id="e91b4-175">此版本包含针对版本 0.11.2003.2506 的小 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="e91b4-175">This release contains minor bugfixes for version 0.11.2003.2506.</span></span>

## <a name="version-01120032506"></a><span data-ttu-id="e91b4-176">版本 0.11.2003.2506</span><span class="sxs-lookup"><span data-stu-id="e91b4-176">Version 0.11.2003.2506</span></span>

<span data-ttu-id="e91b4-177">发行日期：*2020 年 3 月 26 日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-177">*Release date: March 26th, 2020*</span></span>

<span data-ttu-id="e91b4-178">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-178">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-179">对中的访问修饰符的新支持 Q# 。有关详细信息，请参阅 [文件结构](xref:microsoft.quantum.guide.filestructure)</span><span class="sxs-lookup"><span data-stu-id="e91b4-179">New support for access modifiers in Q#, for more information see [File Structures](xref:microsoft.quantum.guide.filestructure)</span></span>
- <span data-ttu-id="e91b4-180">已更新为 .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="e91b4-180">Updated to .NET Core SDK 3.1</span></span>

<span data-ttu-id="e91b4-181">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-181">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01020022610"></a><span data-ttu-id="e91b4-182">版本 0.10.2002.2610</span><span class="sxs-lookup"><span data-stu-id="e91b4-182">Version 0.10.2002.2610</span></span>

<span data-ttu-id="e91b4-183">发行日期：2020 年 2 月 27 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-183">*Release date: February 27th, 2020*</span></span>

<span data-ttu-id="e91b4-184">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-184">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-185">新的量子机器学习库。有关详细信息，请参阅我们的 [QML 文档页](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview)</span><span class="sxs-lookup"><span data-stu-id="e91b4-185">New Quantum Machine Learning library, for more information go to our [QML docs page](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview)</span></span>
- <span data-ttu-id="e91b4-186">我 Q# 的 bug 修复，在加载 NuGet 包时，性能提高了 10-20 倍</span><span class="sxs-lookup"><span data-stu-id="e91b4-186">IQ# bug fixes, resulting in up to a 10-20x performance increase when loading NuGet packages</span></span>

<span data-ttu-id="e91b4-187">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-187">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01020012831"></a><span data-ttu-id="e91b4-188">版本 0.10.2001.2831</span><span class="sxs-lookup"><span data-stu-id="e91b4-188">Version 0.10.2001.2831</span></span>

<span data-ttu-id="e91b4-189">发行日期：2020 年 1 月 29 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-189">*Release date: January 29th, 2020*</span></span>

<span data-ttu-id="e91b4-190">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-190">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-191">新的 Microsoft.Quantum.SDK NuGet 包。在创建新项目时，它将替换 Microsoft.Quantum.Development.Kit 包。</span><span class="sxs-lookup"><span data-stu-id="e91b4-191">New Microsoft.Quantum.SDK NuGet package which will replace Microsoft.Quantum.Development.Kit NuGet package when creating new projects.</span></span> <span data-ttu-id="e91b4-192">现有项目会继续支持 Microsoft.Quantum.Development.Kit NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="e91b4-192">Microsoft.Quantum.Development.Kit NuGet package will continue to be supported for existing projects.</span></span> 
- <span data-ttu-id="e91b4-193">支持 Q# 编译器扩展，这是由新的程序包 NuGet 提供支持的。有关详细信息，请参阅[Github 上的文档](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler)、[编译器扩展示例](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions)和[ Q# 开发博客](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)</span><span class="sxs-lookup"><span data-stu-id="e91b4-193">Support for Q# compiler extensions, enabled by the new Microsoft.Quantum.SDK NuGet packge, for more information see the [documentation on Github](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler), the [compiler extensions sample](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions) and the [Q# Dev Blog](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)</span></span>
- <span data-ttu-id="e91b4-194">添加了对 .NET Core 3.1 的支持。强烈建议安装版本 3.1.100，因为使用旧 .NET Core SDK 版本进行生成可能会导致问题</span><span class="sxs-lookup"><span data-stu-id="e91b4-194">Added support for .NET Core 3.1, it is highly recommended to have version 3.1.100 installed since building with older .NET Core SDK versions may cause issues</span></span>
- <span data-ttu-id="e91b4-195">Microsoft.Quantum.QsCompiler.Experimental 下提供新的编译器转换</span><span class="sxs-lookup"><span data-stu-id="e91b4-195">New compiler transformations available under Microsoft.Quantum.QsCompiler.Experimental</span></span>
- <span data-ttu-id="e91b4-196">用于在 I 中将输出状态向量作为 HTML 公开的新功能Q#</span><span class="sxs-lookup"><span data-stu-id="e91b4-196">New functionality to expose output state vectors as HTML in IQ#</span></span>
- <span data-ttu-id="e91b4-197">针对 Hadamard 和 SWAP 测试向 Microsoft.Quantum.Characterization 添加了对 EstimateFrequencyA 的支持</span><span class="sxs-lookup"><span data-stu-id="e91b4-197">Added support for EstimateFrequencyA to Microsoft.Quantum.Characterization for Hadamard and SWAP tests</span></span>
- <span data-ttu-id="e91b4-198">AmplitudeAmplification 命名空间现在使用 Q# 样式指南</span><span class="sxs-lookup"><span data-stu-id="e91b4-198">AmplitudeAmplification namespace now uses Q# style guide</span></span>

<span data-ttu-id="e91b4-199">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-199">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01019120501"></a><span data-ttu-id="e91b4-200">版本 0.10.1912.0501</span><span class="sxs-lookup"><span data-stu-id="e91b4-200">Version 0.10.1912.0501</span></span>

<span data-ttu-id="e91b4-201">发行日期：*2019 年 12 月 5 日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-201">*Release date: December 5th, 2019*</span></span>

<span data-ttu-id="e91b4-202">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-202">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-203">用于单元测试的新测试属性 Q# ，请参阅[此处](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test)的更新 API 文档和更新的[here](xref:microsoft.quantum.guide.testingdebugging)测试 & 调试指南</span><span class="sxs-lookup"><span data-stu-id="e91b4-203">New Test attribute for Q# unit testing, see updated API documentation [here](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) and updated testing & debugging guide [here](xref:microsoft.quantum.guide.testingdebugging)</span></span>
- <span data-ttu-id="e91b4-204">在出现 Q# 程序执行错误时添加了堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="e91b4-204">Added stack trace in the case of a Q# program execution error</span></span>
- <span data-ttu-id="e91b4-205">对 Visual Studio Code 中的断点的支持（由于 [OmniSharp C# Visual Studio Code 扩展](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)中的更新）</span><span class="sxs-lookup"><span data-stu-id="e91b4-205">Support for breakpoints in Visual Studio Code due to an update in the [OmniSharp C# Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span></span>

<span data-ttu-id="e91b4-206">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-206">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01019111607"></a><span data-ttu-id="e91b4-207">版本 0.10.1911.1607</span><span class="sxs-lookup"><span data-stu-id="e91b4-207">Version 0.10.1911.1607</span></span>

<span data-ttu-id="e91b4-208">发行日期：*2019 年 11 月 17 日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-208">*Release date: November 17th, 2019*</span></span>

<span data-ttu-id="e91b4-209">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-209">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-210">[Quantum Katas](https://github.com/Microsoft/QuantumKatas) 和 Jupyter 笔记本的性能修复</span><span class="sxs-lookup"><span data-stu-id="e91b4-210">Performance fix for [Quantum Katas](https://github.com/Microsoft/QuantumKatas) and Jupyter notebooks</span></span>

<span data-ttu-id="e91b4-211">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-211">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  


## <a name="version-0101911307"></a><span data-ttu-id="e91b4-212">版本 0.10.1911.307</span><span class="sxs-lookup"><span data-stu-id="e91b4-212">Version 0.10.1911.307</span></span>

<span data-ttu-id="e91b4-213">发行日期：*2019 年 11 月 1 日*</span><span class="sxs-lookup"><span data-stu-id="e91b4-213">*Release date: November 1st, 2019*</span></span>

<span data-ttu-id="e91b4-214">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-214">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-215">更新了 Visual Studio Code 和 Visual Studio 扩展，以便将语言服务器部署为独立可执行文件，从而消除了 .NET Core SDK 版本依赖项</span><span class="sxs-lookup"><span data-stu-id="e91b4-215">Updates to Visual Studio Code & Visual Studio extensions to deploy language server as a self-contained executable, eliminating the .NET Core SDK version dependency</span></span>  
- <span data-ttu-id="e91b4-216">迁移到 .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e91b4-216">Migration to .NET Core 3.0</span></span>
- <span data-ttu-id="e91b4-217">对 Microsoft.Quantum.Simulation.Core.IOperationFactory 进行了中断性变更，引入了新的 `Fail` 方法。</span><span class="sxs-lookup"><span data-stu-id="e91b4-217">Breaking change to Microsoft.Quantum.Simulation.Core.IOperationFactory with introduction of new `Fail` method.</span></span> <span data-ttu-id="e91b4-218">它仅影响不扩展 SimulatorBase 的自定义模拟器。</span><span class="sxs-lookup"><span data-stu-id="e91b4-218">It affects only custom simulators that do not extend SimulatorBase.</span></span> <span data-ttu-id="e91b4-219">有关更多详细信息，请[查看 GitHub 上的拉取请求](https://github.com/microsoft/qsharp-runtime/pull/59)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-219">For more details, [view the pull request on GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).</span></span>
- <span data-ttu-id="e91b4-220">对已弃用属性的新支持</span><span class="sxs-lookup"><span data-stu-id="e91b4-220">New support for Deprecated attributes</span></span>

<span data-ttu-id="e91b4-221">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-221">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-0919093002"></a><span data-ttu-id="e91b4-222">版本 0.9.1909.3002</span><span class="sxs-lookup"><span data-stu-id="e91b4-222">Version 0.9.1909.3002</span></span>

<span data-ttu-id="e91b4-223">发行日期：2019 年 9 月 30 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-223">*Release date: September 30th, 2019*</span></span>

<span data-ttu-id="e91b4-224">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-224">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-225">新支持 Q# Visual Studio 2019 中的代码完成 (版本 16.3 & 更高版本) & Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e91b4-225">New support for Q# code completion in Visual Studio 2019 (versions 16.3 & later) & Visual Studio Code</span></span>
- <span data-ttu-id="e91b4-226">量子添加器的新[量子 Kata](https://github.com/Microsoft/QuantumKatas)</span><span class="sxs-lookup"><span data-stu-id="e91b4-226">New [Quantum Kata](https://github.com/Microsoft/QuantumKatas) for quantum adders</span></span>

<span data-ttu-id="e91b4-227">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-227">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-09-packagereference-0919082902"></a><span data-ttu-id="e91b4-228">版本 0.9 (PackageReference 0.9.1908.2902)</span><span class="sxs-lookup"><span data-stu-id="e91b4-228">Version 0.9 (*PackageReference 0.9.1908.2902*)</span></span>

<span data-ttu-id="e91b4-229">发行日期：2019 年 8 月 29 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-229">*Release date: August 29th, 2019*</span></span>

<span data-ttu-id="e91b4-230">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-230">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-231">新支持中的[语态语句](xref:microsoft.quantum.guide.operationsfunctions#conjugations)Q#</span><span class="sxs-lookup"><span data-stu-id="e91b4-231">New support for [conjugation statements](xref:microsoft.quantum.guide.operationsfunctions#conjugations) in Q#</span></span>
- <span data-ttu-id="e91b4-232">编译器中新的代码操作，例如：“replace with”、“add documentation”和简单数组项更新</span><span class="sxs-lookup"><span data-stu-id="e91b4-232">New code actions in the compiler, such as: "replace with", "add documentation", and simple array item update</span></span>
- <span data-ttu-id="e91b4-233">已将安装模板和新项目命令添加到 Visual Studio Code 扩展</span><span class="sxs-lookup"><span data-stu-id="e91b4-233">Added install template and new project commands to Visual Studio Code extension</span></span>
- <span data-ttu-id="e91b4-234">添加了 ApplyIf 连结符的新变体，例如 [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span><span class="sxs-lookup"><span data-stu-id="e91b4-234">Added new variants of ApplyIf combinator such as [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span></span>
- <span data-ttu-id="e91b4-235">已转换为 Jupyter Notebook 的其他[量子 Katas](https://github.com/Microsoft/QuantumKatas)</span><span class="sxs-lookup"><span data-stu-id="e91b4-235">Additional [Quantum Katas](https://github.com/Microsoft/QuantumKatas) converted to Jupyter Notebooks</span></span>
- <span data-ttu-id="e91b4-236">Visual Studio 扩展现在需要 Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e91b4-236">Visual Studio Extension now requires Visual Studio 2019</span></span>

<span data-ttu-id="e91b4-237">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-237">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="e91b4-238">此处汇总了这些更改，以及有关升级现有程序的说明。</span><span class="sxs-lookup"><span data-stu-id="e91b4-238">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="e91b4-239">有关这些更改的详细信息，请参阅[ Q# 开发博客](https://devblogs.microsoft.com/qsharp)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-239">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

## <a name="version-08-packagereference-0819071701"></a><span data-ttu-id="e91b4-240">版本 0.8 (*PackageReference 0.8.1907.1701*)</span><span class="sxs-lookup"><span data-stu-id="e91b4-240">Version 0.8 (*PackageReference 0.8.1907.1701*)</span></span>

<span data-ttu-id="e91b4-241">发行日期：2019 年 7 月 12 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-241">*Release date: July 12, 2019*</span></span>

<span data-ttu-id="e91b4-242">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-242">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-243">用于对数组进行切片的新索引位置，请参阅[语言参考](xref:microsoft.quantum.guide.expressions#array-slices)了解详情。</span><span class="sxs-lookup"><span data-stu-id="e91b4-243">New indexing locations for slicing arrays, [see the language reference](xref:microsoft.quantum.guide.expressions#array-slices) for more information.</span></span>
- <span data-ttu-id="e91b4-244">添加了 [Microsoft 容器注册表](https://github.com/microsoft/ContainerRegistry)中托管的 Dockerfile， [ Q# 有关详细信息，请参阅 I 存储库](https://github.com/microsoft/iqsharp/blob/master/README.md)</span><span class="sxs-lookup"><span data-stu-id="e91b4-244">Added Dockerfile hosted on the [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry), see the [IQ# repository for more information](https://github.com/microsoft/iqsharp/blob/master/README.md)</span></span>
- <span data-ttu-id="e91b4-245">[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的中断性变更、配置设置更新、名称更改；请参阅 [.NET API 浏览器](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)了解更新后的名称。</span><span class="sxs-lookup"><span data-stu-id="e91b4-245">Breaking change for [the trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), update to configuration settings, name changes; see the [.NET API Browser for the updated names](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).</span></span>

<span data-ttu-id="e91b4-246">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-246">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-07-packagereference-0719053109"></a><span data-ttu-id="e91b4-247">版本 0.7 (*PackageReference 0.7.1905.3109*)</span><span class="sxs-lookup"><span data-stu-id="e91b4-247">Version 0.7 (*PackageReference 0.7.1905.3109*)</span></span>

<span data-ttu-id="e91b4-248">发行日期：2019 年 5 月 31 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-248">*Release date: May 31, 2019*</span></span>

<span data-ttu-id="e91b4-249">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-249">This release contains the following:</span></span>
- <span data-ttu-id="e91b4-250">向语言添加的内容 Q# ，</span><span class="sxs-lookup"><span data-stu-id="e91b4-250">additions to the Q# language,</span></span> 
- <span data-ttu-id="e91b4-251">化学库的更新、</span><span class="sxs-lookup"><span data-stu-id="e91b4-251">updates to the chemistry library,</span></span> 
- <span data-ttu-id="e91b4-252">新的数字库。</span><span class="sxs-lookup"><span data-stu-id="e91b4-252">a new numerics library.</span></span>

<span data-ttu-id="e91b4-253">有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的信息，请参阅已结束的 PR 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e91b4-253">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="e91b4-254">此处汇总了这些更改，以及有关升级现有程序的说明。</span><span class="sxs-lookup"><span data-stu-id="e91b4-254">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="e91b4-255">有关这些更改的详细信息，请参阅[ Q# 开发博客](https://devblogs.microsoft.com/qsharp)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-255">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

### <a name="no-locq-language-syntax"></a><span data-ttu-id="e91b4-256">Q# 语言语法</span><span class="sxs-lookup"><span data-stu-id="e91b4-256">Q# language syntax</span></span>
<span data-ttu-id="e91b4-257">此版本添加了新 Q# 语言语法：</span><span class="sxs-lookup"><span data-stu-id="e91b4-257">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="e91b4-258">添加了[用户定义类型](xref:microsoft.quantum.guide.types#user-defined-types)的命名项。</span><span class="sxs-lookup"><span data-stu-id="e91b4-258">Add named items for [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>  
* <span data-ttu-id="e91b4-259">现可将用户定义类型构造函数用作函数。</span><span class="sxs-lookup"><span data-stu-id="e91b4-259">User-defined type constructors can now be used as functions.</span></span>
* <span data-ttu-id="e91b4-260">在用户定义类型中添加了对 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 和 [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) 的支持。</span><span class="sxs-lookup"><span data-stu-id="e91b4-260">Add support for [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) and [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) in user-defined types.</span></span>
* <span data-ttu-id="e91b4-261">[repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) 循环的修复块现在是可选项。</span><span class="sxs-lookup"><span data-stu-id="e91b4-261">Fixup-block for [repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) loops is now optional.</span></span>
* <span data-ttu-id="e91b4-262">我们现支持在函数中（而不是在操作中）使用 while 循环。</span><span class="sxs-lookup"><span data-stu-id="e91b4-262">We now support while loops in functions (not in operations).</span></span>

### <a name="library"></a><span data-ttu-id="e91b4-263">库</span><span class="sxs-lookup"><span data-stu-id="e91b4-263">Library</span></span> 

<span data-ttu-id="e91b4-264">此版本添加了数字库：详细了解如何[使用新的数字库](xref:microsoft.quantum.numerics.usage)并尝试[新的示例](https://github.com/microsoft/quantum/tree/master/Numerics)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-264">This release adds a numerics library: Learn more about how to [use the new numerics library](xref:microsoft.quantum.numerics.usage) and try out the [new samples](https://github.com/microsoft/quantum/tree/master/Numerics).</span></span>  <span data-ttu-id="e91b4-265">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-265">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102).</span></span>  

<span data-ttu-id="e91b4-266">此版本重新组织、扩展并更新了化学库：</span><span class="sxs-lookup"><span data-stu-id="e91b4-266">This release reorganizes extends and updates the chemistry library:</span></span>
* <span data-ttu-id="e91b4-267">改进组件模块化、可扩展性和常规代码清理。</span><span class="sxs-lookup"><span data-stu-id="e91b4-267">Improves modularity of components, extensibility, general code cleanup.</span></span>  <span data-ttu-id="e91b4-268">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-268">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).</span></span>
* <span data-ttu-id="e91b4-269">添加了对[多参考波函数](xref:microsoft.quantum.chemistry.concepts.multireference)（稀疏多参考波函数和单一耦合群集）的支持。</span><span class="sxs-lookup"><span data-stu-id="e91b4-269">Add support for [multi-reference wavefunctions](xref:microsoft.quantum.chemistry.concepts.multireference), both sparse multi-reference wavefunctions and unitary coupled cluster.</span></span>  <span data-ttu-id="e91b4-270">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-270">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>
* <span data-ttu-id="e91b4-271">（谢谢！）[1QBit](https://1qbit.com) 参与者 ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit))：使用变分拟设的能量评估。</span><span class="sxs-lookup"><span data-stu-id="e91b4-271">(Thank you!) [1QBit](https://1qbit.com) contributor ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Energy evaluation using variational ansatz.</span></span> <span data-ttu-id="e91b4-272">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-272">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120).</span></span>
* <span data-ttu-id="e91b4-273">将 [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 架构更新为新[版本 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2)，并添加单一耦合群集规范。</span><span class="sxs-lookup"><span data-stu-id="e91b4-273">Updating [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema to new [version 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), adding unitary coupled cluster specification.</span></span> <span data-ttu-id="e91b4-274">[问题 #65](https://github.com/microsoft/QuantumLibraries/issues/65)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-274">[Issue #65](https://github.com/microsoft/QuantumLibraries/issues/65).</span></span>
* <span data-ttu-id="e91b4-275">将 Python 互操作性添加到化学库函数。</span><span class="sxs-lookup"><span data-stu-id="e91b4-275">Adding Python interoperability to chemistry library functions.</span></span> <span data-ttu-id="e91b4-276">尝试此[示例](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-276">Try out this [sample](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration).</span></span> <span data-ttu-id="e91b4-277">[问题 53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR 110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-277">[Issue #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>

## <a name="version-061905"></a><span data-ttu-id="e91b4-278">版本 0.6.1905</span><span class="sxs-lookup"><span data-stu-id="e91b4-278">Version 0.6.1905</span></span>

<span data-ttu-id="e91b4-279">发行日期：2019 年 5 月 3 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-279">*Release date: May 3, 2019*</span></span>

<span data-ttu-id="e91b4-280">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-280">This release contains the following:</span></span>
- <span data-ttu-id="e91b4-281">对语言进行更改 Q# ，</span><span class="sxs-lookup"><span data-stu-id="e91b4-281">makes changes to the Q# language,</span></span> 
- <span data-ttu-id="e91b4-282">重构量子开发工具包库、</span><span class="sxs-lookup"><span data-stu-id="e91b4-282">restructures the Quantum Development Kit libraries,</span></span> 
- <span data-ttu-id="e91b4-283">添加了新示例，以及</span><span class="sxs-lookup"><span data-stu-id="e91b4-283">adds new samples, and</span></span> 
- <span data-ttu-id="e91b4-284">修复 bug。</span><span class="sxs-lookup"><span data-stu-id="e91b4-284">fixes bugs.</span></span>  <span data-ttu-id="e91b4-285">适用于[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的多个已结束的 PR。</span><span class="sxs-lookup"><span data-stu-id="e91b4-285">Several closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="e91b4-286">此处汇总了这些更改，以及有关升级现有程序的说明。</span><span class="sxs-lookup"><span data-stu-id="e91b4-286">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="e91b4-287">有关这些更改的详细信息，请参阅 devblogs.microsoft.com/qsharp。</span><span class="sxs-lookup"><span data-stu-id="e91b4-287">You can read more about these changes on devblogs.microsoft.com/qsharp.</span></span>

### <a name="no-locq-language-syntax"></a><span data-ttu-id="e91b4-288">Q# 语言语法</span><span class="sxs-lookup"><span data-stu-id="e91b4-288">Q# language syntax</span></span>
<span data-ttu-id="e91b4-289">此版本添加了新 Q# 语言语法：</span><span class="sxs-lookup"><span data-stu-id="e91b4-289">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="e91b4-290">使用 `+` 运算符添加了[用于表示量子操作专用化的简单方式](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)（控制和伴随）。</span><span class="sxs-lookup"><span data-stu-id="e91b4-290">Add a [shorthand way to express specializations of quantum operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (control and adjoints) with `+` operators.</span></span>  <span data-ttu-id="e91b4-291">旧语法已弃用。</span><span class="sxs-lookup"><span data-stu-id="e91b4-291">The old syntax is deprecated.</span></span>  <span data-ttu-id="e91b4-292">使用旧语法（例如 `: adjoint`）的程序将继续运行，但会生成编译时警告。</span><span class="sxs-lookup"><span data-stu-id="e91b4-292">Programs that use the old syntax (e.g., `: adjoint`) will continue to work, but a compile time warning will be generated.</span></span>  
* <span data-ttu-id="e91b4-293">添加了用于 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 的新运算符 `w/`，它可用于将数组创建表示为现有数组的修改。</span><span class="sxs-lookup"><span data-stu-id="e91b4-293">Add a new operator for [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions), `w/`, can be used to express array creation as a modification of an existing array.</span></span>
* <span data-ttu-id="e91b4-294">添加了常用的 [apply-and-update 语句](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols)，例如 `+=` 和 `w/=`。</span><span class="sxs-lookup"><span data-stu-id="e91b4-294">Add the common [apply-and-update statement](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols), e.g., `+=`, `w/=`.</span></span>
* <span data-ttu-id="e91b4-295">添加了一种用于在[开放式指令](xref:microsoft.quantum.guide.filestructure#open-directives)中指定命名空间短名称的方法。</span><span class="sxs-lookup"><span data-stu-id="e91b4-295">Add a way to specify a short name for namespaces in [open directives](xref:microsoft.quantum.guide.filestructure#open-directives).</span></span>

<span data-ttu-id="e91b4-296">在此版本中，我们不再允许在 set 语句的左侧指定数组元素。</span><span class="sxs-lookup"><span data-stu-id="e91b4-296">With this release, we no longer allow an array element to be specified on the left side of a set statement.</span></span>  <span data-ttu-id="e91b4-297">这是因为该语法意味着数组在实际上是可变的，操作的结果始终是创建新数组并加以修改。</span><span class="sxs-lookup"><span data-stu-id="e91b4-297">This is because that syntax implies that arrays are mutable when in fact, the result of the operation has always been the creation of a new array with the modification.</span></span>  <span data-ttu-id="e91b4-298">系统将生成编译器错误，建议使用新新的 copy-and-update 运算符 `w/` 来达到相同的结果。</span><span class="sxs-lookup"><span data-stu-id="e91b4-298">Instead, a compiler error will be generated with a suggestion to use the new copy-and-update operator, `w/`, to accomplish the same result.</span></span>  

### <a name="library-restructuring"></a><span data-ttu-id="e91b4-299">库重构</span><span class="sxs-lookup"><span data-stu-id="e91b4-299">Library restructuring</span></span>
<span data-ttu-id="e91b4-300">此版本重新组织库，使它们的增长保持一致：</span><span class="sxs-lookup"><span data-stu-id="e91b4-300">This release reorganizes the libraries to enable their growth in a consistent way:</span></span>
* <span data-ttu-id="e91b4-301">将 Microsoft.Quantum.Primitive 命名空间重命名为 Microsoft.Quantum.Intrinsic。</span><span class="sxs-lookup"><span data-stu-id="e91b4-301">Renames the Microsoft.Quantum.Primitive namespace  to Microsoft.Quantum.Intrinsic.</span></span>  <span data-ttu-id="e91b4-302">这些操作由目标计算机实现。</span><span class="sxs-lookup"><span data-stu-id="e91b4-302">These operations are implemented by the target machine.</span></span>  <span data-ttu-id="e91b4-303">Microsoft.Quantum.Primitive 命名空间已弃用。</span><span class="sxs-lookup"><span data-stu-id="e91b4-303">The Microsoft.Quantum.Primitive namespace is deprecated.</span></span>  <span data-ttu-id="e91b4-304">运行时警告将建议程序何时使用弃用的名称来调用操作和函数。</span><span class="sxs-lookup"><span data-stu-id="e91b4-304">A runtime warning will advise when programs call operations and functions using deprecated names.</span></span>

* <span data-ttu-id="e91b4-305">将 Microsoft.Quantum.Canon 包重命名为 Microsoft.Quantum.Standard。</span><span class="sxs-lookup"><span data-stu-id="e91b4-305">Renames the Microsoft.Quantum.Canon package to Microsoft.Quantum.Standard.</span></span>  <span data-ttu-id="e91b4-306">此包包含大多数程序通用的命名空间 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-306">This package contains namespaces that are common to most Q# programs.</span></span>  <span data-ttu-id="e91b4-307">这包括：</span><span class="sxs-lookup"><span data-stu-id="e91b4-307">This includes:</span></span>  
    - <span data-ttu-id="e91b4-308">Microsoft.Quantum.Canon，适合常见操作</span><span class="sxs-lookup"><span data-stu-id="e91b4-308">Microsoft.Quantum.Canon for common operations</span></span>
    - <span data-ttu-id="e91b4-309">Microsoft.Quantum.Arithmetic，适合常规算术操作</span><span class="sxs-lookup"><span data-stu-id="e91b4-309">Microsoft.Quantum.Arithmetic for general purpose arithmetic operations</span></span>
    - <span data-ttu-id="e91b4-310">Microsoft.Quantum.Preparation，适合用于准备量子位状态的操作</span><span class="sxs-lookup"><span data-stu-id="e91b4-310">Microsoft.Quantum.Preparation for operations used to prepare qubit state</span></span>
    - <span data-ttu-id="e91b4-311">Microsoft.Quantum.Simulation，适合模拟函数</span><span class="sxs-lookup"><span data-stu-id="e91b4-311">Microsoft.Quantum.Simulation for simulation functionality</span></span>

<span data-ttu-id="e91b4-312">进行此更改后，如果程序包含适用于 Microsoft.Quatum.Canon 命名空间的单个“open”语句，且引用了已移至其他三个新命名空间的操作，则可能会遇到生成错误。</span><span class="sxs-lookup"><span data-stu-id="e91b4-312">With this change, programs that include a single "open" statement for the namespace Microsoft.Quatum.Canon may encounter build errors if the program references operations that were moved to the other three new namespaces.</span></span>  <span data-ttu-id="e91b4-313">为三个新的命名空间添加其他 open 语句是解决此问题的直接方法。</span><span class="sxs-lookup"><span data-stu-id="e91b4-313">Adding the additional open statements for the three new namespaces is a straightforward way to resolve this issue.</span></span>  

* <span data-ttu-id="e91b4-314">已弃用几个命名空间，因为其中的操作已重新组织到其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="e91b4-314">Several namespaces have been deprecated as the operations within have been reorganized to other namespaces.</span></span> <span data-ttu-id="e91b4-315">使用这些命名空间的程序将继续运行，并且编译时警告将指示在其中定义操作的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e91b4-315">Programs that use these namespaces will continue to work, and a compile time warning will denote the namespace where the operation is defined.</span></span>  

* <span data-ttu-id="e91b4-316">Microsoft.Quantum.Arithmetic 命名空间已标准化为使用 <xref:microsoft.quantum.arithmetic.littleendian> 用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="e91b4-316">The Microsoft.Quantum.Arithmetic namespace has been normalized to use the <xref:microsoft.quantum.arithmetic.littleendian> user-defined type.</span></span> <span data-ttu-id="e91b4-317">需要转换为小端时，请使用函数 [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-317">Use the function [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) when needed to convert to little endian.</span></span>  

* <span data-ttu-id="e91b4-318">多个 callables (函数和操作) 的名称已更改为符合[ Q# 样式指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-318">The names of several callables (functions and operations) have been changed to conform to the [Q# Style Guide](xref:microsoft.quantum.contributing.style).</span></span>  <span data-ttu-id="e91b4-319">旧的可调用对象的名称已弃用。</span><span class="sxs-lookup"><span data-stu-id="e91b4-319">The old callable names are deprecated.</span></span>  <span data-ttu-id="e91b4-320">使用旧的可调用对象的程序将继续处理编译时警告。</span><span class="sxs-lookup"><span data-stu-id="e91b4-320">Programs that use the old callables will continue to work with a compile time warning.</span></span> 

### <a name="new-samples"></a><span data-ttu-id="e91b4-321">新示例</span><span class="sxs-lookup"><span data-stu-id="e91b4-321">New Samples</span></span>

<span data-ttu-id="e91b4-322">添加了 [ Q# 与 F # 驱动程序一起使用的示例](https://github.com/Microsoft/Quantum/pull/164)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-322">We added a [sample of using Q# with F# driver](https://github.com/Microsoft/Quantum/pull/164).</span></span>  

<span data-ttu-id="e91b4-323">谢谢你们：</span><span class="sxs-lookup"><span data-stu-id="e91b4-323">**Thank you!**</span></span> <span data-ttu-id="e91b4-324">在 http://github.com/Microsoft/Quantum 向我们的开放代码库发布内容的以下参与者。</span><span class="sxs-lookup"><span data-stu-id="e91b4-324">to the following contributor to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="e91b4-325">这些贡献大大增加了丰富的代码示例 Q# ：</span><span class="sxs-lookup"><span data-stu-id="e91b4-325">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="e91b4-326">Mathias Soeken ([@msoeken](https://github.com/msoeken))：Oracle 函数合成。</span><span class="sxs-lookup"><span data-stu-id="e91b4-326">Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle function synthesis.</span></span> <span data-ttu-id="e91b4-327">[PR #135](https://github.com/Microsoft/Quantum/pull/135)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-327">[PR #135](https://github.com/Microsoft/Quantum/pull/135).</span></span>

### <a name="migrating-existing-projects-to-061905"></a><span data-ttu-id="e91b4-328">将现有项目迁移到 0.6.1905。</span><span class="sxs-lookup"><span data-stu-id="e91b4-328">Migrating existing projects to 0.6.1905.</span></span>

<span data-ttu-id="e91b4-329">请参阅[安装指南](xref:microsoft.quantum.install)，以更新 QDK。</span><span class="sxs-lookup"><span data-stu-id="e91b4-329">See the [install guide](xref:microsoft.quantum.install) to update the QDK.</span></span>
  
<span data-ttu-id="e91b4-330">如果有 Q# 来自量程开发工具包版本0.5 的现有项目，请执行以下步骤将这些项目迁移到最新版本。</span><span class="sxs-lookup"><span data-stu-id="e91b4-330">If you have existing Q# projects from version 0.5 of the Quantum Development Kit, the following are the steps to migrate those projects to the newest version.</span></span>

1. <span data-ttu-id="e91b4-331">项目需要按顺序升级。</span><span class="sxs-lookup"><span data-stu-id="e91b4-331">Projects need to be upgraded in order.</span></span>  <span data-ttu-id="e91b4-332">如果解决方案包含多个项目，请按引用顺序更新每个项目。</span><span class="sxs-lookup"><span data-stu-id="e91b4-332">If you have a solution with multiple projects, update each project in the order they are referenced.</span></span>
2. <span data-ttu-id="e91b4-333">在命令提示符下，运行 `dotnet clean` 以删除所有现有的二进制文件和中间文件。</span><span class="sxs-lookup"><span data-stu-id="e91b4-333">From a command prompt, Run `dotnet clean` to remove all existing binaries and intermediate files.</span></span>
3. <span data-ttu-id="e91b4-334">在文本编辑器中，编辑 .csproj 文件，将所有“Microsoft.Quantum”`PackageReference` 的版本更改为版本 0.6.1904，并将“Microsoft.Quantum.Canon”包名称更改为“Microsoft.Quantum.Standard”，例如：</span><span class="sxs-lookup"><span data-stu-id="e91b4-334">In a text editor, edit the .csproj file to change the version of all the "Microsoft.Quantum" `PackageReference` to version 0.6.1904, and change the "Microsoft.Quantum.Canon" package name to "Microsoft.Quantum.Standard", for example:</span></span>

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. <span data-ttu-id="e91b4-335">在命令提示符下，运行以下命令： `dotnet msbuild`</span><span class="sxs-lookup"><span data-stu-id="e91b4-335">From the command prompt, run this command: `dotnet msbuild`</span></span>  
5. <span data-ttu-id="e91b4-336">运行此命令后，可能仍需要手动解决因上述更改所导致的错误。</span><span class="sxs-lookup"><span data-stu-id="e91b4-336">After running this, you might still need to manually address errors due to changes listed above.</span></span>  <span data-ttu-id="e91b4-337">在许多情况下，Visual Studio 或 Visual Studio Code 中的 IntelliSense 会报告这些错误。</span><span class="sxs-lookup"><span data-stu-id="e91b4-337">In many cases, these errors will also be reported by IntelliSense in Visual Studio or Visual Studio Code.</span></span>
    - <span data-ttu-id="e91b4-338">在 Visual Studio 2019 或 Visual Studio Code 中，打开项目的根文件夹或包含的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e91b4-338">Open the root folder of the project or the containing solution in Visual Studio 2019 or Visual Studio Code.</span></span>
    - <span data-ttu-id="e91b4-339">在编辑器中打开 qs 文件后，应会 Q# 在 "输出" 窗口中看到语言扩展的输出。</span><span class="sxs-lookup"><span data-stu-id="e91b4-339">After opening a .qs file in the editor, you should see the output of the Q# language extension in the output window.</span></span>
    - <span data-ttu-id="e91b4-340">成功加载项目后（输出窗口中会出现相应指示），打开每个文件并手动解决所有剩余问题。</span><span class="sxs-lookup"><span data-stu-id="e91b4-340">After the project has loaded successfully (indicated in the output window) open each file and manually to address all remaining issues.</span></span>

> [!NOTE]
> * <span data-ttu-id="e91b4-341">对于0.6 版本，量子开发工具包附带的语言服务器不支持多个工作区。</span><span class="sxs-lookup"><span data-stu-id="e91b4-341">For the 0.6 release, the language server included with the Quantum Development Kit does not support multiple workspaces.</span></span>
> * <span data-ttu-id="e91b4-342">若要在 Visual Studio Code 中处理项目，请打开包含项目本身和所有引用项目的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="e91b4-342">In order to work with a project in Visual Studio Code, open the root folder containing the project itself and all referenced projects.</span></span>   
> * <span data-ttu-id="e91b4-343">若要在 Visual Studio 中处理解决方案，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e91b4-343">In order to work with a solution in Visual Studio, all projects contained in the solution need to be in the same folder as the solution or in one of its subfolders.</span></span>  
> * <span data-ttu-id="e91b4-344">不支持在迁移到 0.6 和更高版本的项目与使用较低版本的包的项目之间进行引用。</span><span class="sxs-lookup"><span data-stu-id="e91b4-344">References between projects migrated to 0.6 and higher and projects using older package versions are **not** supported.</span></span>

## <a name="version-051904"></a><span data-ttu-id="e91b4-345">版本 0.5.1904</span><span class="sxs-lookup"><span data-stu-id="e91b4-345">Version 0.5.1904</span></span>

<span data-ttu-id="e91b4-346">发行日期：2019 年 4 月 15 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-346">*Release date: April 15, 2019*</span></span>

<span data-ttu-id="e91b4-347">此版本包含 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="e91b4-347">This release contains bug fixes.</span></span>


## <a name="version-051903"></a><span data-ttu-id="e91b4-348">版本 0.5.1903</span><span class="sxs-lookup"><span data-stu-id="e91b4-348">Version 0.5.1903</span></span>

<span data-ttu-id="e91b4-349">发行日期：2019 年 3 月 27 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-349">*Release date: March 27, 2019*</span></span>

<span data-ttu-id="e91b4-350">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-350">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-351">增加了对 Jupyter Notebook 的支持，这提供了一种了解方法 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-351">Adds support for Jupyter Notebook, which offers a great way to learn about Q#.</span></span>  <span data-ttu-id="e91b4-352">[查看新的 Jupyter Notebook 示例，并了解如何编写自己的 Notebooks](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-352">[Check out new Jupyter Notebook samples and learn how to write your own Notebooks](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="e91b4-353">将整数加法器算法添加到了量子 Canon 库中。</span><span class="sxs-lookup"><span data-stu-id="e91b4-353">Adds integer adder arithmetic to the Quantum Canon library.</span></span>  <span data-ttu-id="e91b4-354">另请参阅[描述如何使用新的整数加法器](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb)的 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="e91b4-354">See also a Jupyter Notebook that [describes how to use the new integer adders](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).</span></span>

- <span data-ttu-id="e91b4-355">针对社区报告的 DumpRegister 问题的 bug 修复 ([#148](https://github.com/Microsoft/Quantum/issues/148))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-355">Bug fix for DumpRegister issue reported by the community ([#148](https://github.com/Microsoft/Quantum/issues/148)).</span></span>

- <span data-ttu-id="e91b4-356">添加了从 [using 语句](xref:microsoft.quantum.guide.qubits#allocating-qubits)中返回的功能。</span><span class="sxs-lookup"><span data-stu-id="e91b4-356">Added ability to return from within a [using statement](xref:microsoft.quantum.guide.qubits#allocating-qubits).</span></span>

- <span data-ttu-id="e91b4-357">改版了[入门指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-357">Revamped [getting started guide](xref:microsoft.quantum.install).</span></span>


## <a name="version-051902"></a><span data-ttu-id="e91b4-358">版本 0.5.1902</span><span class="sxs-lookup"><span data-stu-id="e91b4-358">Version 0.5.1902</span></span>

<span data-ttu-id="e91b4-359">发行日期：2019 年 2 月 27 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-359">*Release date: February 27, 2019*</span></span>

<span data-ttu-id="e91b4-360">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-360">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-361">添加了对跨平台 Python 主机的支持。</span><span class="sxs-lookup"><span data-stu-id="e91b4-361">Adds support for a cross-platform Python host.</span></span>  <span data-ttu-id="e91b4-362">`qsharp`用于 python 的包可让你轻松地 Q# 从 Python 内模拟操作和功能。</span><span class="sxs-lookup"><span data-stu-id="e91b4-362">The `qsharp` package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="e91b4-363">了解有关 [Python 互操作性](xref:microsoft.quantum.install)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-363">Learn more about [Python interoperability](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="e91b4-364">Visual Studio 和 Visual Studio Code 扩展现支持符号重命名（例如，函数和操作）。</span><span class="sxs-lookup"><span data-stu-id="e91b4-364">The Visual Studio and Visual Studio Code extensions now support renaming of symbols (e.g., functions and operations).</span></span>

- <span data-ttu-id="e91b4-365">Visual Studio 扩展现可安装在 Visual Studio 2019 上。</span><span class="sxs-lookup"><span data-stu-id="e91b4-365">The Visual Studio extension can now be installed on Visual Studio 2019.</span></span>

## <a name="version-041901"></a><span data-ttu-id="e91b4-366">版本 0.4.1901</span><span class="sxs-lookup"><span data-stu-id="e91b4-366">Version 0.4.1901</span></span>

<span data-ttu-id="e91b4-367">发行日期：2019 年 1 月 30 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-367">*Release date: January 30, 2019*</span></span>

<span data-ttu-id="e91b4-368">此版本包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="e91b4-368">This release contains the following:</span></span>

- <span data-ttu-id="e91b4-369">添加了对新的基元类型 BigInt 的支持，该类型表示任意大小的有符号整数。</span><span class="sxs-lookup"><span data-stu-id="e91b4-369">adds support for a new primitive type, BigInt, which represents a signed integer of arbitrary size.</span></span>  <span data-ttu-id="e91b4-370">了解有关 [BigInt 类型](xref:microsoft.quantum.guide.types)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-370">Learn more about [BigInt type](xref:microsoft.quantum.guide.types).</span></span>
- <span data-ttu-id="e91b4-371">添加了新的 Toffoli 模拟器，这是一种特殊用途的快速模拟器，可模拟 X、CNOT 和多方控制 X 量子操作（具有大量的量子位）。</span><span class="sxs-lookup"><span data-stu-id="e91b4-371">adds new Toffoli simulator, a special purpose fast simulator that can simulate X, CNOT and multi-controlled X quantum operations with very large numbers of qubits.</span></span>  <span data-ttu-id="e91b4-372">了解有关 [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-372">Learn more about [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator).</span></span>
- <span data-ttu-id="e91b4-373">添加了一种简单的资源估计器，用于估算 Q# 在量程计算机上运行给定实例操作所需的资源。</span><span class="sxs-lookup"><span data-stu-id="e91b4-373">adds a simple resource estimator that estimates the resources required to run a given instancee of a Q# operation on a quantum computer.</span></span>  <span data-ttu-id="e91b4-374">了解有关[资源估计器](xref:microsoft.quantum.machines.resources-estimator)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-374">Learn more about the [Resource Estimator](xref:microsoft.quantum.machines.resources-estimator).</span></span>


## <a name="version-0318112802"></a><span data-ttu-id="e91b4-375">版本 0.3.1811.2802</span><span class="sxs-lookup"><span data-stu-id="e91b4-375">Version 0.3.1811.2802</span></span>

<span data-ttu-id="e91b4-376">发行日期：2018 年 11 月 28 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-376">*Release date: November 28, 2018*</span></span>

<span data-ttu-id="e91b4-377">尽管 VS Code 扩展未使用它，但在与 `event-stream` NPM 包相关的 [扩展清除](https://code.visualstudio.com/blogs/2018/11/26/event-stream)过程中，它已被标记并从商城中删除。</span><span class="sxs-lookup"><span data-stu-id="e91b4-377">Even though our VS Code extension was not using it, it was flagged and removed from the marketplace during [the extensions purge](https://code.visualstudio.com/blogs/2018/11/26/event-stream) related to the `event-stream` NPM package.</span></span> <span data-ttu-id="e91b4-378">此版本删除了所有可使扩展触发任何红色标记的运行时依赖项。</span><span class="sxs-lookup"><span data-stu-id="e91b4-378">This version removes all runtime dependencies that could make the extension trigger any red flags.</span></span>

<span data-ttu-id="e91b4-379">如果以前安装了该扩展，则需要访问 Visual Studio Marketplace 上[适用于 Visual Studio Code 的 Microsoft 量子开发工具包](vscode:extension/quantum.quantum-devkit-vscode)扩展并按“安装”，再次安装该扩展。</span><span class="sxs-lookup"><span data-stu-id="e91b4-379">If you had previously installed the extension you will need to install it again by visiting the [Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) extension on the Visual Studio Marketplace and press Install.</span></span> <span data-ttu-id="e91b4-380">对此产生的不便，我们深表歉意。</span><span class="sxs-lookup"><span data-stu-id="e91b4-380">We are sorry about the inconvenience.</span></span>


## <a name="version-0318111511"></a><span data-ttu-id="e91b4-381">版本 0.3.1811.1511</span><span class="sxs-lookup"><span data-stu-id="e91b4-381">Version 0.3.1811.1511</span></span>

<span data-ttu-id="e91b4-382">发行日期：2018 年 11 月 20 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-382">*Release date: November 20, 2018*</span></span>

<span data-ttu-id="e91b4-383">此版本修复了阻止某些用户成功加载 Visual Studio 扩展的 bug。</span><span class="sxs-lookup"><span data-stu-id="e91b4-383">This release fixes a bug that prevented some users to successfully load the Visual Studio extension.</span></span>

## <a name="version-031811203"></a><span data-ttu-id="e91b4-384">版本 0.3.1811.203</span><span class="sxs-lookup"><span data-stu-id="e91b4-384">Version 0.3.1811.203</span></span>

<span data-ttu-id="e91b4-385">发行日期：2018 年 11 月 2 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-385">*Release date: November 2, 2018*</span></span>

<span data-ttu-id="e91b4-386">此版本包含几个 bug 修复，其中包括：</span><span class="sxs-lookup"><span data-stu-id="e91b4-386">This release includes a few bug fixes, including:</span></span>

* <span data-ttu-id="e91b4-387">调用 `DumpMachine` 可能会在某些情况下更改模拟器的状态。</span><span class="sxs-lookup"><span data-stu-id="e91b4-387">Invoking `DumpMachine` could change the state of the simulator under certain situations.</span></span>
* <span data-ttu-id="e91b4-388">删除了使用比 2.1.403 更低的 .NET Core 版本生成项目时的编译警告。</span><span class="sxs-lookup"><span data-stu-id="e91b4-388">Removed compilation warnings when building projects using a version of .NET Core previous to 2.1.403.</span></span>
* <span data-ttu-id="e91b4-389">清理文档，特别是将鼠标悬停在 VS Code 或 Visual Studio 时所显示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="e91b4-389">Clean up of documentation, specially the tooltips shown during mouse hover in VS Code or Visual Studio.</span></span>

## <a name="version-0318102508"></a><span data-ttu-id="e91b4-390">版本 0.3.1810.2508</span><span class="sxs-lookup"><span data-stu-id="e91b4-390">Version 0.3.1810.2508</span></span>

<span data-ttu-id="e91b4-391">发行日期：2018 年 10 月 29 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-391">*Release date: October 29, 2018*</span></span>

<span data-ttu-id="e91b4-392">此版本包含新的语言功能和改善的开发者体验：</span><span class="sxs-lookup"><span data-stu-id="e91b4-392">This release includes new language features and an improved developer experience:</span></span>

* <span data-ttu-id="e91b4-393">此版本包含的语言服务器 Q# ，以及用于 Visual Studio 和 Visual Studio Code 的客户端集成。</span><span class="sxs-lookup"><span data-stu-id="e91b4-393">This release includes a language server for Q#, as well as the client integrations for Visual Studio and Visual Studio Code.</span></span> <span data-ttu-id="e91b4-394">这会启用一组新的 IntelliSense 功能，以及在键入时以波浪下划线的形式发出错误和警告的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="e91b4-394">This enables a new set of IntelliSense features along with live feedback on typing in form of squiggly underlinings of errors and warnings.</span></span> 
* <span data-ttu-id="e91b4-395">总体上看，此更新极大地改善了诊断消息，可以轻松地导航到诊断消息的准确范围，并在显示的悬停信息中提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-395">This update greatly improves diagnostic messages in general, with easy navigation to and precise ranges for diagnostics and additional details in the displayed hover information.</span></span>
* <span data-ttu-id="e91b4-396">Q#语言已经过扩展，使开发人员可以执行常见操作的方式和对语言功能的新增强功能进行了扩展，以有效快速的量程计算。</span><span class="sxs-lookup"><span data-stu-id="e91b4-396">The Q# language has been extended in ways that unifies the ways developers can do common operations and new enhancements to the language features to powerfully express quantum computation.</span></span>  <span data-ttu-id="e91b4-397">在此版本中，对语言进行了重大更改 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-397">There are a handful of breaking changes to the Q# language with this release.</span></span>   

<span data-ttu-id="e91b4-398">此版本还包括新的量子化学库：</span><span class="sxs-lookup"><span data-stu-id="e91b4-398">This release also includes a new quantum chemistry library:</span></span>

* <span data-ttu-id="e91b4-399">该化学库包含新的 Hamiltonian 模拟功能，其中包括：</span><span class="sxs-lookup"><span data-stu-id="e91b4-399">The chemistry library contains new Hamiltonian simulation features, including:</span></span>
    - <span data-ttu-id="e91b4-400">任意偶数顺序的 Trotter–Suzuki 积分器，可提高模拟准确性。</span><span class="sxs-lookup"><span data-stu-id="e91b4-400">Trotter–Suzuki integrators of arbitrary even order for improved simulation accuracy.</span></span>
    - <span data-ttu-id="e91b4-401">量子位化模拟技术，其中进行了特定于化学的优化，可降低 $T$-gate 复杂性。</span><span class="sxs-lookup"><span data-stu-id="e91b4-401">Qubitization simulation technique with chemistry-specific optimizations for reducing $T$-gate complexity.</span></span>
* <span data-ttu-id="e91b4-402">引入了一种新的开源架构，称为 Broombridge 架构（该名称参考了被誉为 Hamiltonians 发源地的[地标](https://en.wikipedia.org/wiki/Broom_Bridge)），用于导入分子表示形式并对其进行模拟。</span><span class="sxs-lookup"><span data-stu-id="e91b4-402">A new open source schema, called Broombridge Schema (in reference to a [landmark](https://en.wikipedia.org/wiki/Broom_Bridge) celebrated as a birthplace of Hamiltonians), is introduced for importing representations of molecules and simulating them.</span></span>
* <span data-ttu-id="e91b4-403">提供使用 Broombridge 架构定义的多个化学表示形式。</span><span class="sxs-lookup"><span data-stu-id="e91b4-403">Multiple chemical representations defined using the Broombridge Schema are provided.</span></span>  <span data-ttu-id="e91b4-404">这些模型由一种开源的高性能计算化学工具 [NWChem](http://www.nwchem-sw.org/) 生成。</span><span class="sxs-lookup"><span data-stu-id="e91b4-404">These models were generated by [NWChem](http://www.nwchem-sw.org/), an open source high-performance computational chemistry tool.</span></span>
* <span data-ttu-id="e91b4-405">教程和示例介绍如何使用化学库和 Broombridge 数据模型执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e91b4-405">Tutorials and Samples describe how to use the chemistry library and the Broombridge data models to:</span></span>
    - <span data-ttu-id="e91b4-406">使用化学库构造简单的 Hamiltonians</span><span class="sxs-lookup"><span data-stu-id="e91b4-406">Construct simple Hamiltonians using the chemistry library</span></span>
    - <span data-ttu-id="e91b4-407">使用阶段估计直观显示氢化锂的基态能量和激发态能量。</span><span class="sxs-lookup"><span data-stu-id="e91b4-407">Visualize ground and excited energies of Lithium Hydride using phase estimation.</span></span>
    - <span data-ttu-id="e91b4-408">执行量子化学模拟的资源评估。</span><span class="sxs-lookup"><span data-stu-id="e91b4-408">Perform resource estimates of quantum chemistry simulation.</span></span>
    - <span data-ttu-id="e91b4-409">估计 Broombridge 架构表示的分子的能级。</span><span class="sxs-lookup"><span data-stu-id="e91b4-409">Estimate energy levels of molecules represented by the Broombridge schema.</span></span>
* <span data-ttu-id="e91b4-410">文档介绍了如何使用 NWChem 为用于的量程模拟生成附加化学模型 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-410">Documentation describes how to use NWChem to generate additional chemical models for quantum simulation with Q#.</span></span>

<span data-ttu-id="e91b4-411">了解有关[量子开发工具包化学库](xref:microsoft.quantum.chemistry.concepts.intro)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-411">Learn more about the [Quantum Development Kit chemistry library](xref:microsoft.quantum.chemistry.concepts.intro).</span></span>

<span data-ttu-id="e91b4-412">使用新的化学库，我们将库划分成新的 GitHub 存储库 [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-412">With the new chemistry library, we are separating out the libraries into a new GitHub repo, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).</span></span>  <span data-ttu-id="e91b4-413">示例保留在 [Microsoft/Quantum](https://github.com/Microsoft/Quantum) 存储库中。</span><span class="sxs-lookup"><span data-stu-id="e91b4-413">The samples remain in the repo [Microsoft/Quantum](https://github.com/Microsoft/Quantum).</span></span>  <span data-ttu-id="e91b4-414">我们欢迎大家参与到这两个库的构建中！</span><span class="sxs-lookup"><span data-stu-id="e91b4-414">We welcome contributions to both!</span></span>

<span data-ttu-id="e91b4-415">此版本包括社区报告的问题对应的 bug 修复和功能：</span><span class="sxs-lookup"><span data-stu-id="e91b4-415">This release includes bug fixes and features for issues reported by the community:</span></span>

* <span data-ttu-id="e91b4-416">Q#的 Intellisense</span><span class="sxs-lookup"><span data-stu-id="e91b4-416">Intellisense for Q#?</span></span> <span data-ttu-id="e91b4-417">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-417">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).</span></span>
* <span data-ttu-id="e91b4-418">.qs 文件 ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-418">.qs files ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).</span></span>
* <span data-ttu-id="e91b4-419">当 if 语句中大括号缩写时，请改进错误消息 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-419">Improve error message when curly braces are abbreviated in if statement ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).</span></span>
* <span data-ttu-id="e91b4-420">支持在可变（重新）绑定上进行元组析构 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-420">Support tuple deconstruction at mutable (re-)binding ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).</span></span>
* <span data-ttu-id="e91b4-421">运行提供的 BitFlipCode 时出错 ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-421">Error Running Provided BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>
* <span data-ttu-id="e91b4-422">H2SimulationGUI 有时会显示较大峰值 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-422">H2SimulationGUI displays big peaks sometimes ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="e91b4-423">社区贡献</span><span class="sxs-lookup"><span data-stu-id="e91b4-423">Community Contributions</span></span>

<span data-ttu-id="e91b4-424">谢谢你们：</span><span class="sxs-lookup"><span data-stu-id="e91b4-424">**Thank you!**</span></span> <span data-ttu-id="e91b4-425">在 http://github.com/Microsoft/Quantum 向我们的开放代码库发布内容的以下参与者。</span><span class="sxs-lookup"><span data-stu-id="e91b4-425">to the following contributors to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="e91b4-426">这些贡献大大增加了丰富的代码示例 Q# ：</span><span class="sxs-lookup"><span data-stu-id="e91b4-426">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="e91b4-427">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)) ： Q# 通过创建一个 QASM 到 Translator 来改善 QASM/开发人员的体验 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-427">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Improved the experience for QASM/Q# developers by creating a QASM to Q# translator.</span></span> <span data-ttu-id="e91b4-428">[PR #58](https://github.com/Microsoft/Quantum/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-428">[PR #58](https://github.com/Microsoft/Quantum/pull/58).</span></span>

* <span data-ttu-id="e91b4-429">Andrew Helwer ([@ahelwer](https://github.com/ahelwer))：提供了实现 CHSH 游戏的示例，该游戏是一个与非区域相关的量子游戏。</span><span class="sxs-lookup"><span data-stu-id="e91b4-429">Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Contributed a sample implementing the CHSH Game, a quantum game related to non-locality.</span></span>  <span data-ttu-id="e91b4-430">[PR #84](https://github.com/Microsoft/Quantum/pull/84)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-430">[PR #84](https://github.com/Microsoft/Quantum/pull/84).</span></span>

<span data-ttu-id="e91b4-431">同样感谢 Rohit Gupta（[@guptarohit](https://github.com/guptarohit)，[PR #90](https://github.com/Microsoft/quantum/pull/90)）、Tanaka Takayoshi（[@tanaka-takayoshi](https://github.com/tanaka-takayoshi)，[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)），以及 Lee James O'Riordan（[@mlxd](https://github.com/mlxd)，[PR #96](https://github.com/Microsoft/Quantum/pull/96)），他们通过分类文档以及更正拼写和错误改善了我们所有人的内容！</span><span class="sxs-lookup"><span data-stu-id="e91b4-431">Thank you also to Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)), and Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) for their work improving the content for all of us through documentation, spelling and typo corrections!</span></span> 

## <a name="version-021809701"></a><span data-ttu-id="e91b4-432">版本 0.2.1809.701</span><span class="sxs-lookup"><span data-stu-id="e91b4-432">Version 0.2.1809.701</span></span>

<span data-ttu-id="e91b4-433">发行日期：2018 年 9 月 10 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-433">*Release date: September 10, 2018*</span></span>

<span data-ttu-id="e91b4-434">此版本包括社区报告的问题对应的 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="e91b4-434">This release includes bug fixes for issues reported by the community.</span></span> <span data-ttu-id="e91b4-435">其中包括：</span><span class="sxs-lookup"><span data-stu-id="e91b4-435">Including:</span></span>

* <span data-ttu-id="e91b4-436">无法使用移位运算符 ([GitHub](https://github.com/Microsoft/Quantum/issues/75))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-436">Unable to use shift operator ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).</span></span>
* <span data-ttu-id="e91b4-437">打印到控制台时，`DumpMachine` / `DumpRegister` 在 `QCTraceSimulator` 上失败 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-437">`DumpMachine` / `DumpRegister` fails on `QCTraceSimulator` when printing to console ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).</span></span>
* <span data-ttu-id="e91b4-438">允许分配 0 个量子位 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-438">Allow allocating 0 qubits ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).</span></span>
* <span data-ttu-id="e91b4-439">`AssertQubitState` 需要显式 Complex() 调用 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-439">`AssertQubitState` requires explicit Complex() call ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).</span></span>
* <span data-ttu-id="e91b4-440">`Measure` 操作始终在 macOS 上返回 `One` ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="e91b4-440">`Measure` operation always returns `One` on macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>

<span data-ttu-id="e91b4-441">谢谢！</span><span class="sxs-lookup"><span data-stu-id="e91b4-441">Thanks!</span></span> 

## <a name="version-0218063001"></a><span data-ttu-id="e91b4-442">版本 0.2.1806.3001</span><span class="sxs-lookup"><span data-stu-id="e91b4-442">Version 0.2.1806.3001</span></span>

<span data-ttu-id="e91b4-443">发行日期：2018 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-443">*Release date: June 30, 2018*</span></span>

<span data-ttu-id="e91b4-444">此版本只是对 [GitHub 上报告 #48 问题](https://github.com/Microsoft/Quantum/issues/48) 进行快速修复 (Q# 如果用户名包含空格) ，则编译失败。</span><span class="sxs-lookup"><span data-stu-id="e91b4-444">This releases is just a quick fix for [issue #48 reported on GitHub](https://github.com/Microsoft/Quantum/issues/48) (Q# compilation fails if user name contains a blank space).</span></span> <span data-ttu-id="e91b4-445">在相应的新版本 (`0.2.1806.3001-preview`) 中遵循与 `0.2.1806.1503` 相同的更新说明。</span><span class="sxs-lookup"><span data-stu-id="e91b4-445">Follow same update instructions as `0.2.1806.1503` with the corresponding new version (`0.2.1806.3001-preview`).</span></span>

## <a name="version-0218061503"></a><span data-ttu-id="e91b4-446">版本 0.2.1806.1503</span><span class="sxs-lookup"><span data-stu-id="e91b4-446">Version 0.2.1806.1503</span></span>

<span data-ttu-id="e91b4-447">发行日期：2018 年 6 月 22 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-447">*Release date: June 22, 2018*</span></span>

<span data-ttu-id="e91b4-448">此版本包含多项社区贡献，并改进了调试体验，提高了性能。</span><span class="sxs-lookup"><span data-stu-id="e91b4-448">This release includes several community contributions as well as an improved debugging experience and improved performance.</span></span>  <span data-ttu-id="e91b4-449">具体来说：</span><span class="sxs-lookup"><span data-stu-id="e91b4-449">Specifically:</span></span>

* <span data-ttu-id="e91b4-450">对 QuantumSimulator 目标计算机的小型和大型模拟进行性能改进。</span><span class="sxs-lookup"><span data-stu-id="e91b4-450">Performance improvements on both small and large simulations for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="e91b4-451">改进了调试功能。</span><span class="sxs-lookup"><span data-stu-id="e91b4-451">Improved debugging functionality.</span></span>
* <span data-ttu-id="e91b4-452">在 bug 修复、新的帮助程序函数、操作和新示例方面的社区贡献。</span><span class="sxs-lookup"><span data-stu-id="e91b4-452">Community contributions in bug fixes, new helper functions, operations and new samples.</span></span>

### <a name="performance-improvements"></a><span data-ttu-id="e91b4-453">性能改进</span><span class="sxs-lookup"><span data-stu-id="e91b4-453">Performance improvements</span></span>

<span data-ttu-id="e91b4-454">此更新包括对所有目标计算机的大量和少量量子位模拟的显著性能改进。</span><span class="sxs-lookup"><span data-stu-id="e91b4-454">This update includes significant performance improvements for simulation of large and small numbers of qubits for all the target machines.</span></span>  <span data-ttu-id="e91b4-455">这种改进在量子开发工具包中的标准示例 H<sub>2</sub> 模拟中非常明显。</span><span class="sxs-lookup"><span data-stu-id="e91b4-455">This improvement is easily visible with the H<sub>2</sub> simulation that is a standard sample in the Quantum Development Kit.</span></span>

### <a name="improved-debugging-functionality"></a><span data-ttu-id="e91b4-456">改进了调试功能</span><span class="sxs-lookup"><span data-stu-id="e91b4-456">Improved debugging functionality</span></span>

<span data-ttu-id="e91b4-457">此更新添加了新的调试功能：</span><span class="sxs-lookup"><span data-stu-id="e91b4-457">This update adds new debugging functionality:</span></span>
* <span data-ttu-id="e91b4-458">添加了 @"microsoft.quantum.extensions.diagnostics.dumpmachine" 和 @"microsoft.quantum.extensions.diagnostics.dumpregister" 两个新操作，可在某个时间点输出有关目标量子计算机的波形函数信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-458">Added two new operations,  @"microsoft.quantum.extensions.diagnostics.dumpmachine" and @"microsoft.quantum.extensions.diagnostics.dumpregister" that output wave function information about the target quantum machine at a point in time.</span></span>  
* <span data-ttu-id="e91b4-459">在 Visual Studio 中，在单个量子位测量到 $\ket{1}$ 的概率现在会自动显示在 QuantumSimulator 目标计算机的调试窗口中。</span><span class="sxs-lookup"><span data-stu-id="e91b4-459">In Visual Studio, the probability of measuring a $\ket{1}$ on a single qubit is now automatically shown in the debugging window for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="e91b4-460">在 Visual Studio 中，改进了“自动”和“局部变量”调试窗口中变量属性的显示 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-460">In Visual Studio, improved the display of variable properties in the **Autos** and **Locals** debug windows.</span></span> 

<span data-ttu-id="e91b4-461">了解有关[测试和调试](xref:microsoft.quantum.guide.testingdebugging)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-461">Learn more about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="e91b4-462">社区贡献</span><span class="sxs-lookup"><span data-stu-id="e91b4-462">Community Contributions</span></span>

<span data-ttu-id="e91b4-463">Q#编码员社区正在不断增长，我们兴奋不已查看第一个用户提供的库和示例，并将其提交到我们的开放基本代码 http://github.com/Microsoft/quantum 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-463">The Q# coder community is growing and we are thrilled to see the first user contributed libraries and samples that were submitted to our open code base at http://github.com/Microsoft/quantum.</span></span>  <span data-ttu-id="e91b4-464">非常感谢！</span><span class="sxs-lookup"><span data-stu-id="e91b4-464">**A big Thank you!**</span></span> <span data-ttu-id="e91b4-465">感谢以下参与者：</span><span class="sxs-lookup"><span data-stu-id="e91b4-465">to the following contributors:</span></span>
* <span data-ttu-id="e91b4-466">Mathias Soeken ([@msoeken](https://github.com/msoeken))：提供了一个定义基于转换的逻辑合成方法的示例，该方法可构造用于实现给定排列的 Toffoli 网络。</span><span class="sxs-lookup"><span data-stu-id="e91b4-466">Mathias Soeken ([@msoeken](https://github.com/msoeken)):  contributed a sample defining a transformation based logic synthesis method that constructs Toffoli networks to implement a given permutation.</span></span> <span data-ttu-id="e91b4-467">代码完全以 Q# 函数和操作的方式编写。</span><span class="sxs-lookup"><span data-stu-id="e91b4-467">The code is written entirely in Q# functions and operations.</span></span>  <span data-ttu-id="e91b4-468">[PR #41](https://github.com/Microsoft/Quantum/pull/41)。</span><span class="sxs-lookup"><span data-stu-id="e91b4-468">[PR #41](https://github.com/Microsoft/Quantum/pull/41).</span></span>
* <span data-ttu-id="e91b4-469">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)) ： MICROSOFT MVP Rolf Huisman 提供了一个示例，该示例从 Q# 代码中为不具有传统控制流和有限量程操作的受限程序类生成平面 QASM 代码。</span><span class="sxs-lookup"><span data-stu-id="e91b4-469">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)): Microsoft MVP Rolf Huisman contributed a sample that generates flat QASM code from Q# code for a restricted class of programs that do not have classical control flow and restricted quantum operations.</span></span> [<span data-ttu-id="e91b4-470">PR #59</span><span class="sxs-lookup"><span data-stu-id="e91b4-470">PR #59</span></span>](https://github.com/Microsoft/Quantum/pull/59)
* <span data-ttu-id="e91b4-471">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314))：通过提交用于受控操作的库函数，帮助改进我们的代码库。</span><span class="sxs-lookup"><span data-stu-id="e91b4-471">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): helped to improve our code base by submitting a library function for controlled operations.</span></span> [<span data-ttu-id="e91b4-472">PR #53</span><span class="sxs-lookup"><span data-stu-id="e91b4-472">PR #53</span></span>](https://github.com/Microsoft/Quantum/pull/53)
* <span data-ttu-id="e91b4-473">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111))：修复 @"microsoft.quantum.canon.quantumphaseestimation" 并新建单元测试。</span><span class="sxs-lookup"><span data-stu-id="e91b4-473">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): fixed @"microsoft.quantum.canon.quantumphaseestimation" and created new unit tests.</span></span>  [<span data-ttu-id="e91b4-474">PR #54</span><span class="sxs-lookup"><span data-stu-id="e91b4-474">PR #54</span></span>](https://github.com/Microsoft/Quantum/pull/54)
* <span data-ttu-id="e91b4-475">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit))：通过确保释放 QuantumSimulator 实例来清除 Teleportation 示例。</span><span class="sxs-lookup"><span data-stu-id="e91b4-475">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): cleaned the Teleportation sample by making sure the QuantumSimulator instance is disposed.</span></span> [<span data-ttu-id="e91b4-476">PR #20</span><span class="sxs-lookup"><span data-stu-id="e91b4-476">PR #20</span></span>](https://github.com/Microsoft/Quantum/pull/20)

<span data-ttu-id="e91b4-477">此外，非常感谢你们：</span><span class="sxs-lookup"><span data-stu-id="e91b4-477">Additionally, a big **Thank You!**</span></span> <span data-ttu-id="e91b4-478">来自商业工程服务团队的 Microsoft 软件工程师参与者，他们在黑客马拉松期间对文档进行了重要的更改。</span><span class="sxs-lookup"><span data-stu-id="e91b4-478">to these Microsoft Software Engineers from the Commercial Engineering Services team contributors who made valuable changes to our documentation during their Hackathon.</span></span>  <span data-ttu-id="e91b4-479">他们作出的更改大大改善了我们所有人的清晰度和载入体验：</span><span class="sxs-lookup"><span data-stu-id="e91b4-479">Their changes vastly improved the clarity and onboarding experience for all of us:</span></span>
* <span data-ttu-id="e91b4-480">Sascha Corti</span><span class="sxs-lookup"><span data-stu-id="e91b4-480">Sascha Corti</span></span>
* <span data-ttu-id="e91b4-481">Mihaela Curmei</span><span class="sxs-lookup"><span data-stu-id="e91b4-481">Mihaela Curmei</span></span>
* <span data-ttu-id="e91b4-482">John Donnelly</span><span class="sxs-lookup"><span data-stu-id="e91b4-482">John Donnelly</span></span>
* <span data-ttu-id="e91b4-483">Kirill Logachev</span><span class="sxs-lookup"><span data-stu-id="e91b4-483">Kirill Logachev</span></span>
* <span data-ttu-id="e91b4-484">Jan Pospisil</span><span class="sxs-lookup"><span data-stu-id="e91b4-484">Jan Pospisil</span></span>
* <span data-ttu-id="e91b4-485">Anita Ramanan</span><span class="sxs-lookup"><span data-stu-id="e91b4-485">Anita Ramanan</span></span>
* <span data-ttu-id="e91b4-486">Frances Tibble</span><span class="sxs-lookup"><span data-stu-id="e91b4-486">Frances Tibble</span></span>
* <span data-ttu-id="e91b4-487">Alessandro Vozza</span><span class="sxs-lookup"><span data-stu-id="e91b4-487">Alessandro Vozza</span></span>

### <a name="update-existing-projects"></a><span data-ttu-id="e91b4-488">更新现有项目</span><span class="sxs-lookup"><span data-stu-id="e91b4-488">Update existing projects</span></span>

<span data-ttu-id="e91b4-489">此版本可完全向后兼容。</span><span class="sxs-lookup"><span data-stu-id="e91b4-489">This release is fully backwards compatible.</span></span> <span data-ttu-id="e91b4-490">只需将项目中的 nuget 包更新为 `0.2.1806.1503-preview` 版本，并执行全部重新生成，即可确保重新生成所有中间文件。</span><span class="sxs-lookup"><span data-stu-id="e91b4-490">Just update the nuget pakages in your projects to version `0.2.1806.1503-preview` and do a **full rebuild** to make sure all intermediate files are regenerated.</span></span>

<span data-ttu-id="e91b4-491">在 Visual Studio 中，按照有关如何[更新包](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package)的常规说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e91b4-491">From Visual Studio, follow the normal instructions on how to [update a package](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).</span></span>

<span data-ttu-id="e91b4-492">若要更新命令行的项目模板，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e91b4-492">To update project templates for the command line, run the following command:</span></span>
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

<span data-ttu-id="e91b4-493">运行此命令后，使用 `dotnet new <project-type> -lang Q#` 创建的任何新项目将自动使用此版本的量子开发工具包。</span><span class="sxs-lookup"><span data-stu-id="e91b4-493">After running this command, any new projects created using `dotnet new <project-type> -lang Q#` will automatically use this version of the Quantum Development Kit.</span></span>

<span data-ttu-id="e91b4-494">若要更新现有项目以使用最新版本，请从每个项目的目录中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e91b4-494">To update an existing project to use the newest version, run the following command from within the directory for each project:</span></span>

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

<span data-ttu-id="e91b4-495">如果现有项目还使用 XUnit 集成进行单元测试，则也可使用类似的命令来更新该包：</span><span class="sxs-lookup"><span data-stu-id="e91b4-495">If an existing project also uses XUnit integration for unit testing, then a similar command can be used to update that package as well:</span></span>
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

<span data-ttu-id="e91b4-496">根据测试项目所使用的 XUnit 版本，可能还需要将 XUnit 更新到 2.3.1：</span><span class="sxs-lookup"><span data-stu-id="e91b4-496">Depending on the version of XUnit that your test project uses, you may also need to update XUnit to 2.3.1:</span></span>
```
dotnet add package xunit -v "2.3.1" 
```

<span data-ttu-id="e91b4-497">更新后，请确保通过以下方式删除先前版本生成的所有临时文件：</span><span class="sxs-lookup"><span data-stu-id="e91b4-497">After the update, make sure you remove all temporary files generated by the previous version by doing:</span></span>
```
dotnet clean 
```

### <a name="known-issues"></a><span data-ttu-id="e91b4-498">已知问题</span><span class="sxs-lookup"><span data-stu-id="e91b4-498">Known Issues</span></span>

<span data-ttu-id="e91b4-499">未报告任何其他已知问题。</span><span class="sxs-lookup"><span data-stu-id="e91b4-499">No aditional known issues to report.</span></span>


## <a name="version-0218022202"></a><span data-ttu-id="e91b4-500">版本 0.2.1802.2202</span><span class="sxs-lookup"><span data-stu-id="e91b4-500">Version 0.2.1802.2202</span></span>

<span data-ttu-id="e91b4-501">发行日期：2018 年 2 月 26 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-501">*Release date: February 26, 2018*</span></span>

<span data-ttu-id="e91b4-502">此版本支持在多个平台上开发、语言互操作和性能增强。</span><span class="sxs-lookup"><span data-stu-id="e91b4-502">This release brings support for development on more platforms, language interoperability, and performance enhancements.</span></span> <span data-ttu-id="e91b4-503">具体来说：</span><span class="sxs-lookup"><span data-stu-id="e91b4-503">Specifically:</span></span>

- <span data-ttu-id="e91b4-504">支持基于 macOS 和 Linux 的开发。</span><span class="sxs-lookup"><span data-stu-id="e91b4-504">Support for macOS- and Linux-based development.</span></span> 
- <span data-ttu-id="e91b4-505">兼容 .NET Core，包括支持跨平台的 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="e91b4-505">.NET Core compatibility, including support for Visual Studio Code across platforms.</span></span>
- <span data-ttu-id="e91b4-506">量子开发工具包库的完整开放源代码许可证。</span><span class="sxs-lookup"><span data-stu-id="e91b4-506">A full Open Source license for the Quantum Development Kit Libraries.</span></span>
- <span data-ttu-id="e91b4-507">提高了需要 20 个或以上量子位的项目的模拟器性能。</span><span class="sxs-lookup"><span data-stu-id="e91b4-507">Improved simulator performance on projects requiring 20 or more qubits.</span></span>
- <span data-ttu-id="e91b4-508">可与 Python 语言（适用于 Windows 的预览版本）互操作。</span><span class="sxs-lookup"><span data-stu-id="e91b4-508">Interoperability with the Python language (preview release available on Windows).</span></span>

### <a name="net-editions"></a><span data-ttu-id="e91b4-509">.NET 版本</span><span class="sxs-lookup"><span data-stu-id="e91b4-509">.NET Editions</span></span>

<span data-ttu-id="e91b4-510">.NET 平台具有两种不同的版本：随 Windows 提供的 .NET Framework，以及在 Windows、macOS 和 Linux 上提供的开源 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="e91b4-510">The .NET platform is available through two different editions, the .NET Framework that is provided with Windows, and the open-source .NET Core that is available on Windows, macOS and Linux.</span></span>
<span data-ttu-id="e91b4-511">在此版本中，量子开发工具包的大部分内容作为 .NET Standard 的库提供，该库是 Framework 和 Core 共用的一组类。</span><span class="sxs-lookup"><span data-stu-id="e91b4-511">With this release, most parts of the Quantum Development Kit are provided as libraries for .NET Standard, the set of classes common to both Framework and Core.</span></span>
<span data-ttu-id="e91b4-512">这些库因此与 .NET Framework 或 .NET Core 的最新版本兼容。</span><span class="sxs-lookup"><span data-stu-id="e91b4-512">These libraries are therefore compatible with recent versions of either .NET Framework or .NET Core.</span></span>

<span data-ttu-id="e91b4-513">因此，为了帮助确保使用量子开发工具包编写的项目尽可能成为可移植项目，我们建议使用量子开发工具包编写的库项目面向 .NET Standard，而控制台应用程序面向 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="e91b4-513">Thus, to help ensure that projects written using the Quantum Development Kit are as portable as possible, we recommend that library projects written using the Quantum Development Kit target .NET Standard, while console applications target .NET Core.</span></span>
<span data-ttu-id="e91b4-514">由于以前版本的量子开发工具包仅支持 .NET Framework，因此可能需要迁移现有项目；有关如何执行此操作的详细信息，请参阅以下内容。</span><span class="sxs-lookup"><span data-stu-id="e91b4-514">Since previous releases of the Quantum Development Kit only supported .NET Framework, you may need to migrate your existing projects; see below for details on how to do this.</span></span>

### <a name="project-migration"></a><span data-ttu-id="e91b4-515">项目迁移</span><span class="sxs-lookup"><span data-stu-id="e91b4-515">Project Migration</span></span>

<span data-ttu-id="e91b4-516">只要未更新使用较低版本的量子开发工具包创建的项目中所用的 NuGet 包，则该项目仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="e91b4-516">Projects created using previous versions of Quantum Development Kit will still work, as long as you don't update the NuGet packages used in them.</span></span> <span data-ttu-id="e91b4-517">若要将现有代码迁移到新版本，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e91b4-517">To migrate existing code to the new version, perform the following steps:</span></span>
1. <span data-ttu-id="e91b4-518">使用正确类型的 Q# 项目模板 (应用程序、库或测试项目) 创建新的 .Net Core 项目。</span><span class="sxs-lookup"><span data-stu-id="e91b4-518">Create a new .NET Core project using the right type of Q# project template (Application, Library or Test Project).</span></span>
2. <span data-ttu-id="e91b4-519">将旧项目中的现有 .qs 和 .cs/.fs 文件复制到新项目（使用“添加”>“现有项”）。</span><span class="sxs-lookup"><span data-stu-id="e91b4-519">Copy existing .qs and .cs/.fs files from the old project to the new project (using Add > Existing Item).</span></span> <span data-ttu-id="e91b4-520">请勿复制 AssemblyInfo.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="e91b4-520">Do not copy the AssemblyInfo.cs file.</span></span>
3. <span data-ttu-id="e91b4-521">生成并运行新项目。</span><span class="sxs-lookup"><span data-stu-id="e91b4-521">Build and run the new project.</span></span>

<span data-ttu-id="e91b4-522">请注意，Microsoft.Quantum.Canon 命名空间的 RandomWalkPhaseEstimation 操作已移动到 [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) 存储库中的 Microsoft.Research.Quantum.RandomWalkPhaseEstimation 命名空间。</span><span class="sxs-lookup"><span data-stu-id="e91b4-522">Please note that the operation RandomWalkPhaseEstimation from the namespace Microsoft.Quantum.Canon was moved into the namespace Microsoft.Research.Quantum.RandomWalkPhaseEstimation in the [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) repository.</span></span>

### <a name="known-issues"></a><span data-ttu-id="e91b4-523">已知问题</span><span class="sxs-lookup"><span data-stu-id="e91b4-523">Known Issues</span></span>

- <span data-ttu-id="e91b4-524">`--filter` `dotnet test` 对于在中编写的测试，该选项无法正常工作 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-524">The `--filter` option to `dotnet test` does not work correctly for tests written in Q#.</span></span>
  <span data-ttu-id="e91b4-525">因此，无法在 Visual Studio Code 中运行单个单元测试;建议 `dotnet test` 在命令提示符处使用来重新运行所有测试。</span><span class="sxs-lookup"><span data-stu-id="e91b4-525">As a result, individual unit tests cannot be run in Visual Studio Code; we recommend using `dotnet test` at the command prompt to re-run all tests.</span></span>

## <a name="version-0118011707"></a><span data-ttu-id="e91b4-526">版本 0.1.1801.1707</span><span class="sxs-lookup"><span data-stu-id="e91b4-526">Version 0.1.1801.1707</span></span>

<span data-ttu-id="e91b4-527">发行日期：2018 年 1 月 18 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-527">*Release date: January 18, 2018*</span></span>

<span data-ttu-id="e91b4-528">此版本修复了社区报告的一些问题。</span><span class="sxs-lookup"><span data-stu-id="e91b4-528">This release fixes some issues reported by the community.</span></span> <span data-ttu-id="e91b4-529">也就是说，</span><span class="sxs-lookup"><span data-stu-id="e91b4-529">Namely:</span></span>

- <span data-ttu-id="e91b4-530">模拟器现适用于不支持 AVX 的早期 CPU。</span><span class="sxs-lookup"><span data-stu-id="e91b4-530">The simulator now works with early non-AVX-enabled CPUs.</span></span>
- <span data-ttu-id="e91b4-531">区域设置不会导致 Q# 分析器失败。</span><span class="sxs-lookup"><span data-stu-id="e91b4-531">Regional decimal settings will not cause the Q# parser to fail.</span></span>
- <span data-ttu-id="e91b4-532">`SignD` 基元操作现返回 `Int`，而不是 `Double`。</span><span class="sxs-lookup"><span data-stu-id="e91b4-532">`SignD` primitive operation now returns `Int` rather than `Double`.</span></span>


## <a name="version-011712901"></a><span data-ttu-id="e91b4-533">版本 0.1.1712.901</span><span class="sxs-lookup"><span data-stu-id="e91b4-533">Version 0.1.1712.901</span></span>

<span data-ttu-id="e91b4-534">发行日期：2017 年 12 月 11 日</span><span class="sxs-lookup"><span data-stu-id="e91b4-534">*Release date: December 11, 2017*</span></span>

### <a name="known-issues"></a><span data-ttu-id="e91b4-535">已知问题</span><span class="sxs-lookup"><span data-stu-id="e91b4-535">Known Issues</span></span>

#### <a name="hardware-and-software-requirements"></a><span data-ttu-id="e91b4-536">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="e91b4-536">Hardware and Software Requirements</span></span>

- <span data-ttu-id="e91b4-537">量子开发工具包随附的模拟器需要安装 64 位的 Microsoft Windows 才能运行。</span><span class="sxs-lookup"><span data-stu-id="e91b4-537">The simulator included with the Quantum Development Kit requires a 64-bit installation of Microsoft Windows to run.</span></span>
- <span data-ttu-id="e91b4-538">Microsoft 的量子模拟器与量子开发工具包一起安装，利用高级矢量扩展 (AVX)，并且需要支持 AVX 的 CPU。</span><span class="sxs-lookup"><span data-stu-id="e91b4-538">Microsoft's quantum simulator, installed with the Quantum Development Kit, utilizes Advanced Vector Extensions (AVX), and requires an AVX-enabled CPU.</span></span> <span data-ttu-id="e91b4-539">2011 年 1 季度 (Sandy Bridge) 或之后推出的 Intel 处理器支持 AVX。</span><span class="sxs-lookup"><span data-stu-id="e91b4-539">Intel processors shipped in Q1 2011 (Sandy Bridge) or later support AVX.</span></span> <span data-ttu-id="e91b4-540">我们正在评估对早期 CPU 的支持，稍后会公布详细信息。</span><span class="sxs-lookup"><span data-stu-id="e91b4-540">We are evaluating support for earlier CPUs and may announce details at a later time.</span></span>

#### <a name="project-creation"></a><span data-ttu-id="e91b4-541">项目创建</span><span class="sxs-lookup"><span data-stu-id="e91b4-541">Project Creation</span></span>

- <span data-ttu-id="e91b4-542">在创建将使用的解决方案 ( .sln) 时 Q# ，解决方案中的每个项目 ( .csproj) 都必须是一个目录。</span><span class="sxs-lookup"><span data-stu-id="e91b4-542">When creating a solution (.sln) that will use Q#, the solution must be one directory higher than each project (.csproj) in the solution.</span></span> <span data-ttu-id="e91b4-543">若要新建解决方案，请确保选中“新建项目”对话框中的“创建解决方案的目录”复选框。</span><span class="sxs-lookup"><span data-stu-id="e91b4-543">When creating a new solution, this can be accomplished by making sure that the "Create directory for solution" checkbox on the "New Project" dialog box is checked.</span></span> <span data-ttu-id="e91b4-544">如果未能创建，则需要手动安装量子开发工具包 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="e91b4-544">If this is not done, the Quantum Development Kit NuGet packages will need to be installed manually.</span></span>

#### Q#

- <span data-ttu-id="e91b4-545">Intellisense 不显示正确的代码错误 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-545">Intellisense does not display proper errors for Q# code.</span></span> <span data-ttu-id="e91b4-546">请确保在 Visual Studio 错误列表中显示生成错误，以查看正确 Q# 错误。</span><span class="sxs-lookup"><span data-stu-id="e91b4-546">Make sure that you are displaying Build errors in the Visual Studio Error List to see correct Q# errors.</span></span> <span data-ttu-id="e91b4-547">另请注意，在 Q# 完成生成之前，将不会显示错误。</span><span class="sxs-lookup"><span data-stu-id="e91b4-547">Also note that Q# errors will not show up until after you've done a build.</span></span>
- <span data-ttu-id="e91b4-548">在部分应用程序中使用可变数组可能导致意外的行为。</span><span class="sxs-lookup"><span data-stu-id="e91b4-548">Using a mutable array in a partial application may lead to unexpected behavior.</span></span>
- <span data-ttu-id="e91b4-549">将不可变数组绑定到可变数组（令 a = b，其中 b 是可变数组）可能会导致意外的行为。</span><span class="sxs-lookup"><span data-stu-id="e91b4-549">Binding an immutable array to a mutable array (let a = b, where b is a mutable array) may lead to unexpected behavior.</span></span>
- <span data-ttu-id="e91b4-550">分析、代码覆盖率和其他 VS 插件可能不会始终 Q# 准确地计算行和块的数量。</span><span class="sxs-lookup"><span data-stu-id="e91b4-550">Profiling, code coverage and other VS plugins may not always count Q# lines and blocks accurately.</span></span>
- <span data-ttu-id="e91b4-551">Q#编译器不验证内插字符串。</span><span class="sxs-lookup"><span data-stu-id="e91b4-551">The Q# compiler does not validate interpolated strings.</span></span> <span data-ttu-id="e91b4-552">可以通过拼写错误的变量名称或在内插字符串中使用表达式来创建 c # 编译错误 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-552">It is possible to create C# compilation errors by misspelling variable names or using expressions in Q# interpolated strings.</span></span>

#### <a name="simulation"></a><span data-ttu-id="e91b4-553">模拟</span><span class="sxs-lookup"><span data-stu-id="e91b4-553">Simulation</span></span>

- <span data-ttu-id="e91b4-554">量子模拟器使用 OpenMP 并行化所需的线性代数。</span><span class="sxs-lookup"><span data-stu-id="e91b4-554">The Quantum Simulator uses OpenMP to parallelize the linear algebra required.</span></span> <span data-ttu-id="e91b4-555">OpenMP 默认使用所有可用的硬件线程，这意味着具有少量的量子位的程序通常运行缓慢，因为所需的协调远多于实际工作。</span><span class="sxs-lookup"><span data-stu-id="e91b4-555">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="e91b4-556">通过将环境变量 OMP_NUM_THREADS 设置为较小数值，可修复此故障。</span><span class="sxs-lookup"><span data-stu-id="e91b4-556">This can be fixed by setting the environment variable OMP_NUM_THREADS to a small number.</span></span> <span data-ttu-id="e91b4-557">作为非常粗略的经验法则，1 个线程最多可以容纳约 4 个量子位，然后每个量子位最好增加一个线程，但这在很大程度上取决于你的算法。</span><span class="sxs-lookup"><span data-stu-id="e91b4-557">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

#### <a name="debugging"></a><span data-ttu-id="e91b4-558">调试</span><span class="sxs-lookup"><span data-stu-id="e91b4-558">Debugging</span></span>

- <span data-ttu-id="e91b4-559">F11 () 中的步骤在代码中不起作用 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e91b4-559">F11 (step in) doesn't work in Q# code.</span></span>
- <span data-ttu-id="e91b4-560">代码 Q# 在断点或单步暂停的代码中突出显示有时是不准确的。</span><span class="sxs-lookup"><span data-stu-id="e91b4-560">Code highlighting in Q# code at a breakpoint or single-step pause is sometimes inaccurate.</span></span> <span data-ttu-id="e91b4-561">虽然系统会突出显示正确的行，但有时突出显示将从行中不正确的列开始和结束。</span><span class="sxs-lookup"><span data-stu-id="e91b4-561">The correct line will be highlighted, but sometimes the highlight will start and end at incorrect columns on the line.</span></span>

#### <a name="testing"></a><span data-ttu-id="e91b4-562">测试</span><span class="sxs-lookup"><span data-stu-id="e91b4-562">Testing</span></span>

- <span data-ttu-id="e91b4-563">必须在 64 位模式下执行测试。</span><span class="sxs-lookup"><span data-stu-id="e91b4-563">Tests must be executed in 64-bit mode.</span></span> <span data-ttu-id="e91b4-564">如果测试失败，并出现 BadImageFormatException，请转到“测试”菜单，依次选择“测试设置”>“默认处理器体系结构”>“X64”。</span><span class="sxs-lookup"><span data-stu-id="e91b4-564">If your tests are failing with a BadImageFormatException, go to the Test menu and select Test Settings > Default Processor Architecture > X64.</span></span>
- <span data-ttu-id="e91b4-565">有些测试需要很长的运行时间，可能需要 5 分钟，具体取决于你的计算机。</span><span class="sxs-lookup"><span data-stu-id="e91b4-565">Some tests take a long time (possibly as much as 5 minutes depending on your computer) to run.</span></span> <span data-ttu-id="e91b4-566">这是正常的，因为有些测试使用超过 20 个量子位；我们目前最大的测试可运行 23 个量子位。</span><span class="sxs-lookup"><span data-stu-id="e91b4-566">This is normal, as some use over twenty qubits; our largest test currently runs on 23 qubits.</span></span>

#### <a name="samples"></a><span data-ttu-id="e91b4-567">示例</span><span class="sxs-lookup"><span data-stu-id="e91b4-567">Samples</span></span>

- <span data-ttu-id="e91b4-568">在某些计算机上，除非将环境变量 OMP_NUM_THREADS 设置为“1”，否则一些小样本可能会运行缓慢。</span><span class="sxs-lookup"><span data-stu-id="e91b4-568">On some machines, some small samples may run slowly unless the environment variable OMP_NUM_THREADS is set to "1".</span></span> <span data-ttu-id="e91b4-569">另请参见“模拟”下的发行说明。</span><span class="sxs-lookup"><span data-stu-id="e91b4-569">See also the release note under "Simulation".</span></span>

#### <a name="libraries"></a><span data-ttu-id="e91b4-570">库</span><span class="sxs-lookup"><span data-stu-id="e91b4-570">Libraries</span></span>

- <span data-ttu-id="e91b4-571">有一个隐含的假设，即以不同的参数传递给操作的量子位都是不同的。</span><span class="sxs-lookup"><span data-stu-id="e91b4-571">There is an implicit assumption that the qubits passed to an operation in different arguments are all distinct.</span></span> <span data-ttu-id="e91b4-572">例如，所有库操作（和所有模拟器）都假定传递给受控 NOT 的两个量子位是不同的量子位。</span><span class="sxs-lookup"><span data-stu-id="e91b4-572">For instance, all of the library operations (and all of the simulators) assume that the two qubits passed to a controlled NOT are different qubits.</span></span> <span data-ttu-id="e91b4-573">违反此假设可能会导致发生无法预料的意外情况。</span><span class="sxs-lookup"><span data-stu-id="e91b4-573">Violating this assumption may lead to unpredictable unexpected.</span></span> <span data-ttu-id="e91b4-574">可以使用量子计算机跟踪器模拟器对此进行测试。</span><span class="sxs-lookup"><span data-stu-id="e91b4-574">It is possible to test for this using the quantum computer tracer simulator.</span></span>
- <span data-ttu-id="e91b4-575">Microsoft.Quantum.Bind 函数可能无法在所有情况下都按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="e91b4-575">The Microsoft.Quantum.Bind function may not act as expected in all cases.</span></span>
- <span data-ttu-id="e91b4-576">在 Microsoft.Quantum.Extensions.Math 命名空间中，尽管基础 System.Math.Sign 函数始终返回整数，但 SignD 函数返回 Double 类型而非 Int 类型。</span><span class="sxs-lookup"><span data-stu-id="e91b4-576">In the Microsoft.Quantum.Extensions.Math namespace, the SignD function returns a Double rather than an Int, although the underlying System.Math.Sign function always returns an integer.</span></span> <span data-ttu-id="e91b4-577">可以安全地将结果与 1.0、-1.0 和 0.0 进行比较，因为这些双精度值均具有精确的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="e91b4-577">It is safe to compare the result against 1.0, -1.0, and 0.0, since these doubles all have exact binary representations.</span></span>
