---
title: IQ# Magic 命令
description: '带有 Q # Jupyter 笔记本的 IQ # 幻命令的快速参考页面'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431013"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="9e0c1-103">IQ# Magic 命令</span><span class="sxs-lookup"><span data-stu-id="9e0c1-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="9e0c1-104">常规</span><span class="sxs-lookup"><span data-stu-id="9e0c1-104">General</span></span>

- <span data-ttu-id="9e0c1-105">`%config`：设置或获取配置首选项。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="9e0c1-106">`%estimate`：在 QuantumSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="9e0c1-107">`%lsmagic`：返回当前可用的所有幻命令的列表。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="9e0c1-108">`%package`：提供加载 Nuget 包的能力。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="9e0c1-109">`%performance`：报告此内核的当前性能指标。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="9e0c1-110">`%simulate`：在 QuantumSimulator 目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="9e0c1-111">`%toffoli`：在 ToffoliSimulator 模拟器目标计算机上运行给定的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="9e0c1-112">`%who`：提供与当前工作区相关的操作。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="9e0c1-113">`%workspace`：返回当前会话中定义的所有操作和函数的列表，该列表以交互方式或从当前工作区加载。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="9e0c1-114">化学</span><span class="sxs-lookup"><span data-stu-id="9e0c1-114">Chemistry</span></span>

- <span data-ttu-id="9e0c1-115">`%chemistry.broombridge`：从 yaml 文件加载并返回 Broombridge 电子结构问题表示形式。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="9e0c1-116">`%chemistry.encode`：将 fermion Hamiltonian 编码为 Q # 可使用的格式。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="9e0c1-117">`%chemistry.fh.add_terms`：向 fermion Hamiltonian 添加术语。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="9e0c1-118">`%chemistry.fh.load`：加载 fermion Hamiltonian 以解决电子结构问题。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="9e0c1-119">此问题是从文件加载的，或作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="9e0c1-120">`%chemistry.inputstate.load`：加载 Broombridge 电子结构问题并返回所选输入状态。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="9e0c1-121">从 Katas 包</span><span class="sxs-lookup"><span data-stu-id="9e0c1-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="9e0c1-122">`%kata`：执行单个测试，并报告测试是否已成功通过。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="9e0c1-123">`%check_kata`：检查单个 kata 测试的引用实现。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="9e0c1-124">具体而言，它将一个任务的引用实现替换为单元，并报告测试是否成功通过。</span><span class="sxs-lookup"><span data-stu-id="9e0c1-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
