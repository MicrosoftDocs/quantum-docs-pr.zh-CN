---
title: 'Q # 标准库中的数学公式'
description: '了解用于内置数据类型的 Q # 标准库中的传统数学函数。'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274405"
---
# <a name="classical-mathematical-functions"></a>传统数学函数 #

这些函数主要用于处理 Q # 内置数据类型 `Int` 、 `Double` 和 `Range` 。

<xref:microsoft.quantum.intrinsic.random>操作具有签名 `(Double[] => Int)` 。
它采用双精度数组作为输入，并将随机选择的索引作为返回到数组中 `Int` 。
选择特定索引的概率与该索引处数组元素的值成正比。 已忽略等于零的 n 个数组元素，并且从不返回它们的索引。
如果任何数组元素小于0，或者如果没有数组元素大于零，则操作将失败。
