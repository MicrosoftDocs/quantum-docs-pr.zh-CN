---
title: IQ# Magic 命令
description: '带有 Q # Jupyter 笔记本的 IQ # 幻命令的快速参考页面'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 2fb542df8723fa437c82b4a1dfada77e22c1d6e4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870528"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="f18b5-103">IQ# Magic 命令</span><span class="sxs-lookup"><span data-stu-id="f18b5-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="f18b5-104">常规</span><span class="sxs-lookup"><span data-stu-id="f18b5-104">General</span></span>

- <span data-ttu-id="f18b5-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config)：允许设置或查询配置选项。</span><span class="sxs-lookup"><span data-stu-id="f18b5-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Allows setting or querying configuration options.</span></span>
- <span data-ttu-id="f18b5-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate)：在 ResourcesEstimator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="f18b5-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Runs a given function or operation on the ResourcesEstimator target machine.</span></span>
- <span data-ttu-id="f18b5-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic)：返回当前可用的所有幻命令的列表。</span><span class="sxs-lookup"><span data-stu-id="f18b5-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="f18b5-108">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package)：提供加载 NuGet 包的能力。</span><span class="sxs-lookup"><span data-stu-id="f18b5-108">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Provides the ability to load a NuGet package.</span></span>
- <span data-ttu-id="f18b5-109">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance)：报告此内核的当前性能指标。</span><span class="sxs-lookup"><span data-stu-id="f18b5-109">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="f18b5-110">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate)：在 QuantumSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="f18b5-110">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="f18b5-111">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)：在 ToffoliSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="f18b5-111">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Runs a given function or operation on the ToffoliSimulator target machine.</span></span>
- <span data-ttu-id="f18b5-112">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who)：列出当前会话中可用的 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="f18b5-112">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Lists the Q# operations available in the current session.</span></span>
- <span data-ttu-id="f18b5-113">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace)：提供与当前工作区相关的操作。</span><span class="sxs-lookup"><span data-stu-id="f18b5-113">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Provides actions related to the current workspace.</span></span>

### <a name="azure-quantum-integration"></a><span data-ttu-id="f18b5-114">Azure 量程集成</span><span class="sxs-lookup"><span data-stu-id="f18b5-114">Azure Quantum integration</span></span>

- <span data-ttu-id="f18b5-115">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect)：连接到 Azure 量程工作区或显示当前连接状态。</span><span class="sxs-lookup"><span data-stu-id="f18b5-115">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Connects to an Azure Quantum workspace or displays current connection status.</span></span>
- <span data-ttu-id="f18b5-116">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute)：在 Azure 量程工作区中执行作业。</span><span class="sxs-lookup"><span data-stu-id="f18b5-116">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Executes a job in an Azure Quantum workspace.</span></span>
- <span data-ttu-id="f18b5-117">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs)：显示当前 Azure 量程工作区中的作业列表。</span><span class="sxs-lookup"><span data-stu-id="f18b5-117">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Displays a list of jobs in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="f18b5-118">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output)：显示当前 Azure 量程工作区中某个作业的结果。</span><span class="sxs-lookup"><span data-stu-id="f18b5-118">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Displays results for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="f18b5-119">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status)：在当前 Azure 量程工作区中显示作业的状态。</span><span class="sxs-lookup"><span data-stu-id="f18b5-119">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Displays status for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="f18b5-120">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit)：将作业提交到 Azure 量程工作区。</span><span class="sxs-lookup"><span data-stu-id="f18b5-120">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Submits a job to an Azure Quantum workspace.</span></span>
- <span data-ttu-id="f18b5-121">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target)：设置或显示 Azure 量程工作区中 Q # 作业提交的活动执行目标。</span><span class="sxs-lookup"><span data-stu-id="f18b5-121">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span>

### <a name="chemistry-from-microsoftquantumchemistry-package"></a><span data-ttu-id="f18b5-122">化学（来自 Microsoft 量子包）</span><span class="sxs-lookup"><span data-stu-id="f18b5-122">Chemistry (from Microsoft.Quantum.Chemistry package)</span></span>

- <span data-ttu-id="f18b5-123">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge)：从 yaml 文件加载并返回 Broombridge 电子结构问题表示形式。</span><span class="sxs-lookup"><span data-stu-id="f18b5-123">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="f18b5-124">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode)：将 fermion Hamiltonian 编码为 Q # 可使用的格式。</span><span class="sxs-lookup"><span data-stu-id="f18b5-124">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="f18b5-125">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms)：向 fermion Hamiltonian 添加术语。</span><span class="sxs-lookup"><span data-stu-id="f18b5-125">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="f18b5-126">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load)：加载 fermion Hamiltonian 以解决电子结构问题。</span><span class="sxs-lookup"><span data-stu-id="f18b5-126">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="f18b5-127">此问题是从文件加载的，或作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="f18b5-127">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="f18b5-128">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load)：加载 Broombridge 电子结构问题并返回所选输入状态。</span><span class="sxs-lookup"><span data-stu-id="f18b5-128">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="katas-from-microsoftquantumkatas-package"></a><span data-ttu-id="f18b5-129">Katas （来自 Katas 包）</span><span class="sxs-lookup"><span data-stu-id="f18b5-129">Katas (from Microsoft.Quantum.Katas package)</span></span>

- <span data-ttu-id="f18b5-130">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata)：执行单个测试，并报告测试是否已成功通过。</span><span class="sxs-lookup"><span data-stu-id="f18b5-130">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="f18b5-131">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata)：检查单个 kata 测试的引用实现。</span><span class="sxs-lookup"><span data-stu-id="f18b5-131">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="f18b5-132">具体而言，它将一个任务的引用实现替换为单元，并报告测试是否成功通过。</span><span class="sxs-lookup"><span data-stu-id="f18b5-132">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
