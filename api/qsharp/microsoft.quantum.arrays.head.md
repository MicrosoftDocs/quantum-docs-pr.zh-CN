---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221107"
---
# <a name="head-function"></a>Head 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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