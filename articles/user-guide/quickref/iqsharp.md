---
title: I Q# 幻命令
description: Q#Jupyter 笔记本的 I 幻命令的快速参考页面 Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: reference
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb6517b782a82c1cb159951af41df9bfde51c0bb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858533"
---
# <a name="ino-locq-magic-commands"></a><span data-ttu-id="b5470-103">I Q# 幻命令</span><span class="sxs-lookup"><span data-stu-id="b5470-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="b5470-104">常规</span><span class="sxs-lookup"><span data-stu-id="b5470-104">General</span></span>

- <span data-ttu-id="b5470-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config)：允许设置或查询配置选项。</span><span class="sxs-lookup"><span data-stu-id="b5470-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Allows setting or querying configuration options.</span></span>
- <span data-ttu-id="b5470-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate)：在 ResourcesEstimator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="b5470-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Runs a given function or operation on the ResourcesEstimator target machine.</span></span>
- <span data-ttu-id="b5470-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic)：返回当前可用的所有幻命令的列表。</span><span class="sxs-lookup"><span data-stu-id="b5470-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="b5470-108">[`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen)：列出当前打开的命名空间及其别名。</span><span class="sxs-lookup"><span data-stu-id="b5470-108">[`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Lists currently opened namespaces and their aliases.</span></span>
- <span data-ttu-id="b5470-109">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package)：提供加载 NuGet 包的能力。</span><span class="sxs-lookup"><span data-stu-id="b5470-109">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Provides the ability to load a NuGet package.</span></span>
- <span data-ttu-id="b5470-110">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance)：报告此内核的当前性能指标。</span><span class="sxs-lookup"><span data-stu-id="b5470-110">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="b5470-111">[`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project)：提供查看或添加 Q# 项目引用的功能。</span><span class="sxs-lookup"><span data-stu-id="b5470-111">[`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Provides the ability to view or add Q# project references.</span></span> 
- <span data-ttu-id="b5470-112">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate)：在 QuantumSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="b5470-112">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="b5470-113">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)：在 ToffoliSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="b5470-113">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Runs a given function or operation on the ToffoliSimulator target machine.</span></span>
- <span data-ttu-id="b5470-114">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who)：列出 Q# 当前会话中可用的操作。</span><span class="sxs-lookup"><span data-stu-id="b5470-114">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Lists the Q# operations available in the current session.</span></span>
- <span data-ttu-id="b5470-115">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace)：提供与当前工作区相关的操作。</span><span class="sxs-lookup"><span data-stu-id="b5470-115">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Provides actions related to the current workspace.</span></span>

### <a name="azure-quantum-integration"></a><span data-ttu-id="b5470-116">Azure 量程集成</span><span class="sxs-lookup"><span data-stu-id="b5470-116">Azure Quantum integration</span></span>

- <span data-ttu-id="b5470-117">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect)：连接到 Azure 量程工作区或显示当前连接状态。</span><span class="sxs-lookup"><span data-stu-id="b5470-117">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Connects to an Azure Quantum workspace or displays current connection status.</span></span>
- <span data-ttu-id="b5470-118">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute)：将作业提交到 Azure 量程工作区并等待完成。</span><span class="sxs-lookup"><span data-stu-id="b5470-118">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Submits a job to an Azure Quantum workspace and waits for completion.</span></span>
- <span data-ttu-id="b5470-119">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs)：显示当前 Azure 量程工作区中的作业列表。</span><span class="sxs-lookup"><span data-stu-id="b5470-119">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Displays a list of jobs in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="b5470-120">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output)：显示当前 Azure 量程工作区中某个作业的结果。</span><span class="sxs-lookup"><span data-stu-id="b5470-120">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Displays results for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="b5470-121">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status)：在当前 Azure 量程工作区中显示作业的状态。</span><span class="sxs-lookup"><span data-stu-id="b5470-121">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Displays status for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="b5470-122">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit)：将作业提交到 Azure 量程工作区。</span><span class="sxs-lookup"><span data-stu-id="b5470-122">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Submits a job to an Azure Quantum workspace.</span></span>
- <span data-ttu-id="b5470-123">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target)： Q# 在 Azure 量程工作区中设置或显示作业提交的活动运行目标。</span><span class="sxs-lookup"><span data-stu-id="b5470-123">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Sets or displays the active run target for Q# job submission in an Azure Quantum workspace.</span></span>

### <a name="chemistry-from-microsoftquantumchemistry-package"></a><span data-ttu-id="b5470-124">来自 Microsoft 量子包的化学 () </span><span class="sxs-lookup"><span data-stu-id="b5470-124">Chemistry (from Microsoft.Quantum.Chemistry package)</span></span>

- <span data-ttu-id="b5470-125">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge)：从 yaml 文件加载并返回 Broombridge 电子结构问题表示形式。</span><span class="sxs-lookup"><span data-stu-id="b5470-125">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="b5470-126">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode)：将 fermion Hamiltonian 编码为可使用的格式 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5470-126">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="b5470-127">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms)：向 fermion Hamiltonian 添加术语。</span><span class="sxs-lookup"><span data-stu-id="b5470-127">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="b5470-128">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load)：加载 fermion Hamiltonian 以解决电子结构问题。</span><span class="sxs-lookup"><span data-stu-id="b5470-128">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="b5470-129">此问题是从文件加载的，或作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="b5470-129">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="b5470-130">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load)：加载 Broombridge 电子结构问题并返回所选输入状态。</span><span class="sxs-lookup"><span data-stu-id="b5470-130">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="katas-from-microsoftquantumkatas-package"></a><span data-ttu-id="b5470-131">Katas (Katas package) </span><span class="sxs-lookup"><span data-stu-id="b5470-131">Katas (from Microsoft.Quantum.Katas package)</span></span>

- <span data-ttu-id="b5470-132">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata)：运行单个测试，并报告测试是否已成功通过。</span><span class="sxs-lookup"><span data-stu-id="b5470-132">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Runs a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="b5470-133">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata)：检查单个 kata 测试的引用实现。</span><span class="sxs-lookup"><span data-stu-id="b5470-133">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="b5470-134">具体而言，它将一个任务的引用实现替换为单元，并报告测试是否成功通过。</span><span class="sxs-lookup"><span data-stu-id="b5470-134">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
