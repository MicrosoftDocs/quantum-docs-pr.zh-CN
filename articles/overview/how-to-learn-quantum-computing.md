---
title: 如何使用 Q# 学习量子计算？
description: 有关基本数学和物理学知识的资源，用于帮助你着手量子计算。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 17fc4e7a73f93a86d981996bf8b59309bccb6e67
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907743"
---
# <a name="how-to-learn-about-quantum-computing"></a>如何了解量子计算？

获取有关学习量子计算和编写第一个程序的指导。 本指南不全面，但却是一个不错的开端。

## <a name="getting-started-overview"></a>入门概述

[Microsoft Quantum 开发工具包入门](xref:microsoft.quantum.welcome)概述了使用 Q# 进行的量子计算，其中的教程介绍了编写第一个 Q# 程序的方法、入门指南，并介绍了如何通过 Q# 量子库来开发量子程序。

## <a name="learning-the-basics-what-do-you-need-to-know"></a>学习基础知识：需要知道的事情

你无需知道量子物理学便可学习 Q# 和量子计算，或开始编写量子应用程序。

这些概念将帮助你了解开始量子程序编码所需的基础知识。  

* [基本量子力学](xref:microsoft.quantum.concepts.intro)：正如我们刚才所说，你无需知道量子物理学便可以开始编码（这是真的！）。 但一些基本的量子力学概念及其数学表示法有助于了解量子程序。

* **线性代数（向量和矩阵）** ：在量子计算中，量子状态由向量表示，而量子运算则是应用于这些向量的线性转换。  这是[有关线性代数的 Jupyter 笔记本教程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)。  也可在有关[矢量和矩阵](xref:microsoft.quantum.concepts.vectors)的概念指南中详细了解线性代数。

* **复杂算术**：量子状态向量的系数为复数。 即使没有它们，你也可以理解某些基本的量子计算概念，但如果想要深入了解，则需要将它们合并到量子工具包中。  这是[有关复杂算术的 Jupyter 笔记本教程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)，介绍了处理量子计算所需的一些数学背景。 

掌握基础知识后，便可以学习如何编写量子程序了。  可通过多种方式来继续操作：

## <a name="do-the-quantum-katas"></a>完成 Quantum Katas

[Quantum Katas](xref:microsoft.quantum.overview.katas) 是自定进度的开放源代码教程系列，旨在同时教授量子计算的元素和 Q# 编程。  每个 kata 都参考了更多的学习资料，你可以通过这些资料学习成功完成 kata 所需的量子计算概念。  

## <a name="dive-into-the-theory"></a>深入探讨理论

你可能想要深入了解量子力学和量子计算的理论。 以下是一系列有用的资料：

* 请从我们的[量子计算概念](xref:microsoft.quantum.concepts.intro)指南开始，其中概述了量子计算的基本概念。
* 《学习如何使用 Python 和 Q# 执行量子计算》（Sarah C. Kaiser 和 Christopher E. Granade）为几乎不具有量子力学经验但有一些编程背景的人提供了精彩的介绍  。
* 《量子计算和量子信息》（Michael A. Nielsen、Isaac L. Chuang）中的内容在量子计算领域引用最多，被奉为圭臬  。 本书假设你拥有最少的量子力学和计算机科学经验。 对于想要细致了解该主题以及正在寻找相关资料以了解高级概念的读者来说，本书是一个不错的选择。
* MIT OpenCourseWare 有一个优秀的[联机课程](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr)，由 Allan Adams 讲授量子力学的基本知识。 非常适合想要更好地了解基础物理学的开发者。

## <a name="join-the-quantum-community"></a>加入量子社区

你不是一个人在孤军奋战，有一大群业余爱好者和专家都愿意为你提供帮助。 不要害怕提问！

* 如果你对 Q# 或量子计算有任何疑问，请随时查看量子计算 StackExchange 网站。 如果找不到自己特定问题的答案，可以提出一个新问题。 
* 请参阅 [Q# 博客](https://devblogs.microsoft.com/qsharp/)和 [Microsoft Quantum 博客](https://cloudblogs.microsoft.com/quantum/)，随时了解有关 Q# 的最新新闻和资源。
* 请查看 [Q# 社区](https://qsharp.community/)和[出色 Q#](https://project-awesome.org/ebraminio/awesome-qsharp)，查找更多资源和资料。

 若要教授有关量子计算的课程，可访问 [Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html)（Microsoft 量子网络），以便获取课程帮助。  

