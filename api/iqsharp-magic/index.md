---
title: IQ# Magic 命令
author: rmshaffer
uid: microsoft.quantum.iqsharp.magic-ref.index
ms.author: rmshaffer
ms.date: 08/25/2020
ms.topic: article
ms.openlocfilehash: d6bf8407e40be092689b38cf90514c88f798cc2f
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88862967"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="832f3-102">IQ# Magic 命令</span><span class="sxs-lookup"><span data-stu-id="832f3-102">IQ# Magic Commands</span></span>
| <span data-ttu-id="832f3-103">Magic 命令</span><span class="sxs-lookup"><span data-stu-id="832f3-103">Magic Command</span></span> | <span data-ttu-id="832f3-104">总结</span><span class="sxs-lookup"><span data-stu-id="832f3-104">Summary</span></span> |
|---------------|---------|
| [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect) | <span data-ttu-id="832f3-105">连接到 Azure Quantum 工作区或显示当前连接状态。</span><span class="sxs-lookup"><span data-stu-id="832f3-105">Connects to an Azure Quantum workspace or displays current connection status.</span></span> |
| [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute) | <span data-ttu-id="832f3-106">在 Azure Quantum 工作区中执行作业。</span><span class="sxs-lookup"><span data-stu-id="832f3-106">Executes a job in an Azure Quantum workspace.</span></span> |
| [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs) | <span data-ttu-id="832f3-107">在 Azure Quantum 工作区中显示作业列表。</span><span class="sxs-lookup"><span data-stu-id="832f3-107">Displays a list of jobs in the current Azure Quantum workspace.</span></span> |
| [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output) | <span data-ttu-id="832f3-108">在当前 Azure Quantum 工作区中显示作业的结果。</span><span class="sxs-lookup"><span data-stu-id="832f3-108">Displays results for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status) | <span data-ttu-id="832f3-109">在当前 Azure Quantum 工作区中显示走也的状态。</span><span class="sxs-lookup"><span data-stu-id="832f3-109">Displays status for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit) | <span data-ttu-id="832f3-110">将作业提交到 Azure Quantum 工作区。</span><span class="sxs-lookup"><span data-stu-id="832f3-110">Submits a job to an Azure Quantum workspace.</span></span> |
| [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target) | <span data-ttu-id="832f3-111">在 Azure Quantum 工作区中设置或显示 Q# 作业提交项的有效执行目标。</span><span class="sxs-lookup"><span data-stu-id="832f3-111">Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span> |
| [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata) | <span data-ttu-id="832f3-112">检查单个 kata 测试的引用实现。</span><span class="sxs-lookup"><span data-stu-id="832f3-112">Checks the reference implementation for a single kata's test.</span></span> |
| [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge) | <span data-ttu-id="832f3-113">从给定的 .yaml 文件加载并返回 Broombridge 电子结构问题表示形式。</span><span class="sxs-lookup"><span data-stu-id="832f3-113">Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span> |
| [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode) | <span data-ttu-id="832f3-114">将费米子 Hamiltonian 编码为 Q# 可使用的格式。</span><span class="sxs-lookup"><span data-stu-id="832f3-114">Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span> |
| [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms) | <span data-ttu-id="832f3-115">向费米子 Hamiltonian 添加字词。</span><span class="sxs-lookup"><span data-stu-id="832f3-115">Adds terms to a fermion Hamiltonian.</span></span> |
| [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load) | <span data-ttu-id="832f3-116">为电子结构问题加载费米子 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="832f3-116">Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="832f3-117">此问题是从文件加载的，或作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="832f3-117">The problem is loaded from a file or passed as an argument.</span></span> |
| [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load) | <span data-ttu-id="832f3-118">加载 Broombridge 电子结构问题并返回所选输入状态。</span><span class="sxs-lookup"><span data-stu-id="832f3-118">Loads Broombridge electronic structure problem and returns selected input state.</span></span> |
| [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config) | <span data-ttu-id="832f3-119">允许设置或查询配置选项。</span><span class="sxs-lookup"><span data-stu-id="832f3-119">Allows setting or querying configuration options.</span></span> |
| [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate) | <span data-ttu-id="832f3-120">在 ResourcesEstimator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="832f3-120">Runs a given function or operation on the ResourcesEstimator target machine.</span></span> |
| [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata) | <span data-ttu-id="832f3-121">执行单个测试。</span><span class="sxs-lookup"><span data-stu-id="832f3-121">Executes a single test.</span></span> |
| [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic) | <span data-ttu-id="832f3-122">返回所有当前可用的 magic 命令的列表。</span><span class="sxs-lookup"><span data-stu-id="832f3-122">Returns a list of all currently available magic commands.</span></span> |
| [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen) | <span data-ttu-id="832f3-123">列出目前已打开的命名空间及其别名。</span><span class="sxs-lookup"><span data-stu-id="832f3-123">Lists currently opened namespaces and their aliases.</span></span> |
| [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package) | <span data-ttu-id="832f3-124">提供加载 NuGet 包的功能。</span><span class="sxs-lookup"><span data-stu-id="832f3-124">Provides the ability to load a NuGet package.</span></span> |
| [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance) | <span data-ttu-id="832f3-125">报告此内核的当前性能指标。</span><span class="sxs-lookup"><span data-stu-id="832f3-125">Reports current performance metrics for this kernel.</span></span> |
| [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project) | <span data-ttu-id="832f3-126">提供查看或添加 Q# 项目引用的功能。</span><span class="sxs-lookup"><span data-stu-id="832f3-126">Provides the ability to view or add Q# project references.</span></span> |
| [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate) | <span data-ttu-id="832f3-127">在 QuantumSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="832f3-127">Runs a given function or operation on the QuantumSimulator target machine.</span></span> |
| [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) | <span data-ttu-id="832f3-128">在 ToffoliSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="832f3-128">Runs a given function or operation on the ToffoliSimulator target machine.</span></span> |
| [`%trace`](xref:microsoft.quantum.iqsharp.magic-ref.trace) | <span data-ttu-id="832f3-129">直观显示给定操作的执行路径。</span><span class="sxs-lookup"><span data-stu-id="832f3-129">Visualizes the execution path of the given operation.</span></span> |
| [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who) | <span data-ttu-id="832f3-130">列出可在当前会话中执行的 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="832f3-130">Lists the Q# operations available in the current session.</span></span> |
| [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace) | <span data-ttu-id="832f3-131">提供与当前工作区相关的操作。</span><span class="sxs-lookup"><span data-stu-id="832f3-131">Provides actions related to the current workspace.</span></span> |
