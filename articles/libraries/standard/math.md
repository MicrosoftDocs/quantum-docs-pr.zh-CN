---
title: 'Q # 标准库中的数学公式'
description: '了解用于内置数据类型的 Q # 标准库中的传统数学函数。'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906145"
---
# <a name="classical-mathematical-functions"></a>传统数学函数 #

这些函数主要用于处理 Q # 内置数据类型 `Int`、`Double`和 `Range`。

<xref:microsoft.quantum.intrinsic.random> 操作的签名 `(Double[] => Int)`。
它采用双精度数组作为输入，并将随机选择的索引作为 `Int`返回到数组中。
选择特定索引的概率与该索引处数组元素的值成正比。 已忽略等于零的 n 个数组元素，并且从不返回它们的索引。
如果任何数组元素小于0，或者如果没有数组元素大于零，则操作将失败。
