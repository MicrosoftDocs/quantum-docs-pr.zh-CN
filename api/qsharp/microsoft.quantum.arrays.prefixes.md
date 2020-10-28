---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 前缀函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696467"
---
# <a name="prefixes-function"></a>前缀函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定一个数组，返回其所有前缀。

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>说明

返回一个数组，其中包含所有前缀（从仅具有第一个元素直到整个数组的数组开始）。

## <a name="input"></a>输入

### <a name="array--t"></a>array： t []

元素的数组。



## <a name="output--t"></a>输出： t [] []



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。