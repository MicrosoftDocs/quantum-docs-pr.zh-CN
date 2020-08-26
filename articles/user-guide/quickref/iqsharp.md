---
title: I Q# 幻命令
description: Q#Jupyter 笔记本的 I 幻命令的快速参考页面 Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1d2d092588e1a5c69d12e5d50377e3e26412c094
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863694"
---
# <a name="ino-locq-magic-commands"></a>I Q# 幻命令

### <a name="general"></a>常规

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config)：允许设置或查询配置选项。
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate)：在 ResourcesEstimator 目标计算机上运行给定的函数或操作。
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic)：返回当前可用的所有幻命令的列表。
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen)：列出当前打开的命名空间及其别名。
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package)：提供加载 NuGet 包的能力。
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance)：报告此内核的当前性能指标。
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project)：提供查看或添加 Q# 项目引用的功能。 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate)：在 QuantumSimulator 目标计算机上运行给定的函数或操作。
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)：在 ToffoliSimulator 目标计算机上运行给定的函数或操作。
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who)：列出 Q# 当前会话中可用的操作。
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace)：提供与当前工作区相关的操作。

### <a name="azure-quantum-integration"></a>Azure 量程集成

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect)：连接到 Azure 量程工作区或显示当前连接状态。
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute)：在 Azure 量程工作区中执行作业。
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs)：显示当前 Azure 量程工作区中的作业列表。
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output)：显示当前 Azure 量程工作区中某个作业的结果。
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status)：在当前 Azure 量程工作区中显示作业的状态。
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit)：将作业提交到 Azure 量程工作区。
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target)： Q# 在 Azure 量程工作区中设置或显示作业提交的活动执行目标。

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>来自 Microsoft 量子包的化学 () 

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge)：从 yaml 文件加载并返回 Broombridge 电子结构问题表示形式。
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode)：将 fermion Hamiltonian 编码为可使用的格式 Q# 。
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms)：向 fermion Hamiltonian 添加术语。
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load)：加载 fermion Hamiltonian 以解决电子结构问题。 此问题是从文件加载的，或作为参数传递。
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load)：加载 Broombridge 电子结构问题并返回所选输入状态。

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (Katas package) 

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata)：执行单个测试，并报告测试是否已成功通过。
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata)：检查单个 kata 测试的引用实现。
    具体而言，它将一个任务的引用实现替换为单元，并报告测试是否成功通过。
