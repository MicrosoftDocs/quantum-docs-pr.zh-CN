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
# <a name="iq-magic-commands"></a>IQ# Magic 命令

### <a name="general"></a>常规

- `%config`：设置或获取配置首选项。
- `%estimate`：在 QuantumSimulator 目标计算机上运行给定的函数或操作。
- `%lsmagic`：返回当前可用的所有幻命令的列表。
- `%package`：提供加载 Nuget 包的能力。
- `%performance`：报告此内核的当前性能指标。
- `%simulate`：在 QuantumSimulator 目标计算机上运行给定的函数或操作。
- `%toffoli`：在 ToffoliSimulator 模拟器目标计算机上运行给定的函数或操作。
- `%who`：提供与当前工作区相关的操作。
- `%workspace`：返回当前会话中定义的所有操作和函数的列表，该列表以交互方式或从当前工作区加载。

### <a name="chemistry"></a>化学

- `%chemistry.broombridge`：从 yaml 文件加载并返回 Broombridge 电子结构问题表示形式。
- `%chemistry.encode`：将 fermion Hamiltonian 编码为 Q # 可使用的格式。
- `%chemistry.fh.add_terms`：向 fermion Hamiltonian 添加术语。
- `%chemistry.fh.load`：加载 fermion Hamiltonian 以解决电子结构问题。 此问题是从文件加载的，或作为参数传递。
- `%chemistry.inputstate.load`：加载 Broombridge 电子结构问题并返回所选输入状态。

### <a name="from-microsoftquantumkatas-package"></a>从 Katas 包

- `%kata`：执行单个测试，并报告测试是否已成功通过。
- `%check_kata`：检查单个 kata 测试的引用实现。
    具体而言，它将一个任务的引用实现替换为单元，并报告测试是否成功通过。
