---
title: 量子化学库简介
description: 了解 Microsoft 量子化学库，以及如何使用它来模拟量子计算机上的电子结构问题。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: 4268eafa5e53c0a026d179503ac6db88652a8f90
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907318"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>量子化学库简介

长期以来，物理系统的模拟在量子计算中一直发挥着核心作用。  这是因为人们普遍认为，量子动力学很难在量子计算机上模拟，这意味着模拟系统的复杂性会随着所讨论的量子系统的大小呈指数增长。  模拟化学和材料科学中的问题可能仍然是量子计算中最令人回味的应用，我们借此能够探索迄今为止我们无法测量或模拟的化学反应机制。  我们借此还可以模拟相关的电子材料，例如高温超导体。 该技术在此领域的应用非常宽广。

本文档的目的是简要介绍如何在量子计算机上模拟电子结构问题，帮助读者理解 Hamiltonian 模拟库在该领域的许多方面发挥的作用。  我们首先简要介绍量子力学，然后讨论如何在其中构建电子系统模型。  然后，我们将讨论如何使用量子计算机来模拟此类量子动力学。  完成后，我们将讨论两种用于将量子动力学编译为基本门序列的方法：Trotter-Suzuki 分解和量子位化。
