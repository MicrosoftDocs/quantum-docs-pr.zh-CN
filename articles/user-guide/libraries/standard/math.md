---
title: 标准库中的数学公式 Q#
description: 了解 Q# 与内置数据类型一起使用的标准库中的传统数学函数。
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833599"
---
# <a name="classical-mathematical-functions"></a>传统数学函数 #

这些函数主要用于处理 Q# 内置的数据类型 `Int` 、 `Double` 和 `Range` 。

<xref:microsoft.quantum.intrinsic.random>操作具有签名 `(Double[] => Int)` 。
它采用双精度数组作为输入，并将随机选择的索引作为返回到数组中 `Int` 。
选择特定索引的概率与该索引处数组元素的值成正比。 已忽略等于零的 n 个数组元素，并且从不返回它们的索引。
如果任何数组元素小于0，或者如果没有数组元素大于零，则操作将失败。
