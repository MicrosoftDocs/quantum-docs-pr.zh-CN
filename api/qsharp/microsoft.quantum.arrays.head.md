---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696508"
---
# <a name="head-function"></a>Head 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


返回数组的第一个元素。

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>输入

### <a name="array--a"></a>array： ' A []

从中获取第一个元素的数组。 数组的长度必须至少为1。



## <a name="output--a"></a>输出： "A

数组的第一个元素。

## <a name="type-parameters"></a>类型参数

### <a name="a"></a>' A

数组元素的类型。