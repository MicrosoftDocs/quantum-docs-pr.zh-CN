---
uid: Microsoft.Quantum.Arrays.Flattened
title: 平展函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696517"
---
# <a name="flattened-function"></a>平展函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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