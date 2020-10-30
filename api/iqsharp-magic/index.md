---
title: IQ# Magic 命令
description: 列出 IQ# Jupyter 内核中可用的 magic 命令。
author: rmshaffer
uid: microsoft.quantum.iqsharp.magic-ref.index
ms.author: ryansha
ms.date: 10/26/2020
ms.topic: article
ms.openlocfilehash: a615c6dac6cdb80ff84cec2b0a3c99fc700efb8e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691145"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="ddd94-103">IQ# Magic 命令</span><span class="sxs-lookup"><span data-stu-id="ddd94-103">IQ# Magic Commands</span></span>
| <span data-ttu-id="ddd94-104">Magic 命令</span><span class="sxs-lookup"><span data-stu-id="ddd94-104">Magic Command</span></span> | <span data-ttu-id="ddd94-105">总结</span><span class="sxs-lookup"><span data-stu-id="ddd94-105">Summary</span></span> |
|---------------|---------|
| [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect) | <span data-ttu-id="ddd94-106">连接到 Azure Quantum 工作区或显示当前连接状态。</span><span class="sxs-lookup"><span data-stu-id="ddd94-106">Connects to an Azure Quantum workspace or displays current connection status.</span></span> |
| [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute) | <span data-ttu-id="ddd94-107">将作业提交到 Azure Quantum 工作区，等待它完成。</span><span class="sxs-lookup"><span data-stu-id="ddd94-107">Submits a job to an Azure Quantum workspace and waits for completion.</span></span> |
| [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs) | <span data-ttu-id="ddd94-108">在 Azure Quantum 工作区中显示作业列表。</span><span class="sxs-lookup"><span data-stu-id="ddd94-108">Displays a list of jobs in the current Azure Quantum workspace.</span></span> |
| [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output) | <span data-ttu-id="ddd94-109">在当前 Azure Quantum 工作区中显示作业的结果。</span><span class="sxs-lookup"><span data-stu-id="ddd94-109">Displays results for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status) | <span data-ttu-id="ddd94-110">在当前 Azure Quantum 工作区中显示走也的状态。</span><span class="sxs-lookup"><span data-stu-id="ddd94-110">Displays status for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit) | <span data-ttu-id="ddd94-111">将作业提交到 Azure Quantum 工作区。</span><span class="sxs-lookup"><span data-stu-id="ddd94-111">Submits a job to an Azure Quantum workspace.</span></span> |
| [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target) | <span data-ttu-id="ddd94-112">在 Azure Quantum 工作区中设置或显示 Q# 作业提交项的有效执行目标。</span><span class="sxs-lookup"><span data-stu-id="ddd94-112">Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span> |
| [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata) | <span data-ttu-id="ddd94-113">检查单个 kata 测试的引用实现。</span><span class="sxs-lookup"><span data-stu-id="ddd94-113">Checks the reference implementation for a single kata's test.</span></span> |
| [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge) | <span data-ttu-id="ddd94-114">从给定的 .yaml 文件加载并返回 Broombridge 电子结构问题表示形式。</span><span class="sxs-lookup"><span data-stu-id="ddd94-114">Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span> |
| [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode) | <span data-ttu-id="ddd94-115">将费米子 Hamiltonian 编码为 Q# 可使用的格式。</span><span class="sxs-lookup"><span data-stu-id="ddd94-115">Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span> |
| [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms) | <span data-ttu-id="ddd94-116">向费米子 Hamiltonian 添加字词。</span><span class="sxs-lookup"><span data-stu-id="ddd94-116">Adds terms to a fermion Hamiltonian.</span></span> |
| [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load) | <span data-ttu-id="ddd94-117">为电子结构问题加载费米子 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="ddd94-117">Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="ddd94-118">此问题是从文件加载的，或作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="ddd94-118">The problem is loaded from a file or passed as an argument.</span></span> |
| [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load) | <span data-ttu-id="ddd94-119">加载 Broombridge 电子结构问题并返回所选输入状态。</span><span class="sxs-lookup"><span data-stu-id="ddd94-119">Loads Broombridge electronic structure problem and returns selected input state.</span></span> |
| [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config) | <span data-ttu-id="ddd94-120">允许设置或查询配置选项。</span><span class="sxs-lookup"><span data-stu-id="ddd94-120">Allows setting or querying configuration options.</span></span> |
| [`%debug`](xref:microsoft.quantum.iqsharp.magic-ref.debug) | <span data-ttu-id="ddd94-121">逐步执行给定的 Q# 操作或函数。</span><span class="sxs-lookup"><span data-stu-id="ddd94-121">Steps through the execution of a given Q# operation or function.</span></span> |
| [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate) | <span data-ttu-id="ddd94-122">在 ResourcesEstimator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="ddd94-122">Runs a given function or operation on the ResourcesEstimator target machine.</span></span> |
| [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata) | <span data-ttu-id="ddd94-123">执行单个测试。</span><span class="sxs-lookup"><span data-stu-id="ddd94-123">Executes a single test.</span></span> |
| [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic) | <span data-ttu-id="ddd94-124">返回所有当前可用的 magic 命令的列表。</span><span class="sxs-lookup"><span data-stu-id="ddd94-124">Returns a list of all currently available magic commands.</span></span> |
| [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen) | <span data-ttu-id="ddd94-125">列出目前已打开的命名空间及其别名。</span><span class="sxs-lookup"><span data-stu-id="ddd94-125">Lists currently opened namespaces and their aliases.</span></span> |
| [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package) | <span data-ttu-id="ddd94-126">提供加载 NuGet 包的功能。</span><span class="sxs-lookup"><span data-stu-id="ddd94-126">Provides the ability to load a NuGet package.</span></span> |
| [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance) | <span data-ttu-id="ddd94-127">报告此内核的当前性能指标。</span><span class="sxs-lookup"><span data-stu-id="ddd94-127">Reports current performance metrics for this kernel.</span></span> |
| [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project) | <span data-ttu-id="ddd94-128">提供查看或添加 Q# 项目引用的功能。</span><span class="sxs-lookup"><span data-stu-id="ddd94-128">Provides the ability to view or add Q# project references.</span></span> |
| [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate) | <span data-ttu-id="ddd94-129">在 QuantumSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="ddd94-129">Runs a given function or operation on the QuantumSimulator target machine.</span></span> |
| [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) | <span data-ttu-id="ddd94-130">在 ToffoliSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="ddd94-130">Runs a given function or operation on the ToffoliSimulator target machine.</span></span> |
| [`%trace`](xref:microsoft.quantum.iqsharp.magic-ref.trace) | <span data-ttu-id="ddd94-131">直观显示给定操作的执行路径。</span><span class="sxs-lookup"><span data-stu-id="ddd94-131">Visualizes the execution path of the given operation.</span></span> |
| [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who) | <span data-ttu-id="ddd94-132">列出可在当前会话中执行的 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="ddd94-132">Lists the Q# operations available in the current session.</span></span> |
| [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace) | <span data-ttu-id="ddd94-133">提供与当前工作区相关的操作。</span><span class="sxs-lookup"><span data-stu-id="ddd94-133">Provides actions related to the current workspace.</span></span> |
