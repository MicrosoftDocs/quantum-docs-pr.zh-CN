---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220087"
---
# <a name="tail-function"></a>Tail 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回数组的最后一个元素。

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>输入

### <a name="array--a"></a>array： ' A []

要获取其最后一个元素的数组。 数组的长度必须至少为1。



## <a name="output--a"></a>输出： "A

数组的最后一个元素。

## <a name="type-parameters"></a>类型参数

### <a name="a"></a>' A

数组元素的类型。