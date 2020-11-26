---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 前缀函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220377"
---
# <a name="prefixes-function"></a>前缀函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定一个数组，返回其所有前缀。

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>描述

返回一个数组，其中包含所有前缀（从仅具有第一个元素直到整个数组的数组开始）。

## <a name="input"></a>输入

### <a name="array--t"></a>array： t []

元素的数组。



## <a name="output--t"></a>输出： t [] []



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。