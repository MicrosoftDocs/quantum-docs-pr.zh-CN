---
uid: Microsoft.Quantum.Arrays.Flattened
title: 平展函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221209"
---
# <a name="flattened-function"></a>平展函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定数组的数组，返回所有数组的串联。

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a>输入

### <a name="arrays--t"></a>数组： t [] []

数组的数组。



## <a name="output--t"></a>输出： t []

所有数组的串联。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。