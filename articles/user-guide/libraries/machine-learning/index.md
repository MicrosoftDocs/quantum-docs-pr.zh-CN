---
title: 量子机器学习包简介 | Microsoft Docs
description: 量子机器学习包简介
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: conceptual
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e36948a216a06d76b99cd451bbfac6f5defd7c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858795"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>量子机器学习库简介

量子机器学习库是一个用 Q# 编写的 API，用于运行混合量子/经典机器学习试验。 该库用于：

- 加载你自己的数据，以便通过量子模拟器进行分类

- 通过示例和教程将你引入量子机器学习领域

与当前的经典机器学习框架相比，性能预期会降低（请记住，所有内容都在计算成本已经很高昂的量子设备模拟基础上运行）。

本文档的目的是：

- 简要介绍用于混合量子/经典学习的机器学习工具（以 Q\# 编写）。
- 介绍机器学习概念，尤其是其在以量子线路为中心的分类器（也称量子顺序分类器）中的实现。
- 提供一组有关基础知识的教程，这些基础知识是开始使用库提供的工具所需的。
- 讨论此类分类器的训练和验证方法，以及如何将其转换为库提供的特定 Q\# 操作。

此库中实现的模型基于 [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)（以线路为中心的量子分类器）中提供的量子-经典训练方案
