---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 前缀函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845513"
---
# <a name="prefixes-function"></a>前缀函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```