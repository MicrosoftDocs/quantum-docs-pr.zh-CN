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
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="d1ab2-103">量子机器学习库简介</span><span class="sxs-lookup"><span data-stu-id="d1ab2-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="d1ab2-104">量子机器学习库是一个用 Q# 编写的 API，用于运行混合量子/经典机器学习试验。</span><span class="sxs-lookup"><span data-stu-id="d1ab2-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="d1ab2-105">该库用于：</span><span class="sxs-lookup"><span data-stu-id="d1ab2-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="d1ab2-106">加载你自己的数据，以便通过量子模拟器进行分类</span><span class="sxs-lookup"><span data-stu-id="d1ab2-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="d1ab2-107">通过示例和教程将你引入量子机器学习领域</span><span class="sxs-lookup"><span data-stu-id="d1ab2-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="d1ab2-108">与当前的经典机器学习框架相比，性能预期会降低（请记住，所有内容都在计算成本已经很高昂的量子设备模拟基础上运行）。</span><span class="sxs-lookup"><span data-stu-id="d1ab2-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="d1ab2-109">本文档的目的是：</span><span class="sxs-lookup"><span data-stu-id="d1ab2-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="d1ab2-110">简要介绍用于混合量子/经典学习的机器学习工具（以 Q\# 编写）。</span><span class="sxs-lookup"><span data-stu-id="d1ab2-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="d1ab2-111">介绍机器学习概念，尤其是其在以量子线路为中心的分类器（也称量子顺序分类器）中的实现。</span><span class="sxs-lookup"><span data-stu-id="d1ab2-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="d1ab2-112">提供一组有关基础知识的教程，这些基础知识是开始使用库提供的工具所需的。</span><span class="sxs-lookup"><span data-stu-id="d1ab2-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="d1ab2-113">讨论此类分类器的训练和验证方法，以及如何将其转换为库提供的特定 Q\# 操作。</span><span class="sxs-lookup"><span data-stu-id="d1ab2-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="d1ab2-114">此库中实现的模型基于 [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)（以线路为中心的量子分类器）中提供的量子-经典训练方案</span><span class="sxs-lookup"><span data-stu-id="d1ab2-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
