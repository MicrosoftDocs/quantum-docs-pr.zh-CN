---
title: Q# 编程语言 | Microsoft Docs
description: Q# 编程语言
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: d8759b9f043d2e13f4b0c97d54bd824c7e87d6de
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035265"
---
# <a name="the-q-programming-language"></a>Q# 编程语言

# <a name="introduction"></a>介绍

量子计算的自然模型是将量子计算机视为协处理器，类似于用于 GPU、FPGA 和其他副处理器的计算机。
主要控制逻辑在经典“主机”计算机上运行经典代码。
在适当情况下，如有必要，主机程序可以调用在副处理器上运行的子例程。
子例程完成后，主机程序将获取对子例程结果的访问权限。

Q# (Q-sharp) 是用于表示量子算法的特定于域的编程语言。
它用于在经典主机程序和计算机的控制下编写在量子副处理器上执行的子例程。
在量子处理器广泛使用之前，Q# 子例程在模拟器上执行。

Q# 提供一小部分基元类型，以及用于创建新的结构化类型的两种方法（数组和元组）。
它支持使用循环和 if/then 语句编写程序的基本过程模型。
Q# 中的顶级构造是用户定义的类型、操作和函数。

以下部分详细介绍：
- [类型模型](xref:microsoft.quantum.language.type-model)
- [表达式](xref:microsoft.quantum.language.expressions)
- [语句](xref:microsoft.quantum.language.statements)
- [文件结构](xref:microsoft.quantum.language.file-structure)

# <a name="conventions"></a>约定

我们正在努力确保在所有情况下都能一致地使用常见标点符号。
我们预计这会使 Q# 更易于学习和阅读，因为这些标记始终表示相同的含义，相同的概念始终以相同的方式表示。

具体而言：

- 分号 `;` 用于结束语句或单行指令。
  它不用于任何其他用途。
- 逗号 `,` 用于分隔序列的元素。 它用于元组文本、数组文本、参数列表、元组定义和类型列表。 **在早期版本的更改中，`;` 不再支持作为数组文本分隔符。**
- 冒号 `:` 用于引入类型批注。 它主要用于可调用签名。
  由于冒号始终引入类型签名，因此 0.3 中引入的三元条件运算符使用竖线 `|` 来分隔 true 值和 false 值；因此，Q# 使用 `cond ? tval | fval`（而不是冒号）作为 C 中的分隔符。
  
