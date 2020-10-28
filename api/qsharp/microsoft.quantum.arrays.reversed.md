---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反转函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696462"
---
# <a name="reversed-function"></a>反转函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


创建一个数组，该数组包含与输入数组相同的元素，但其顺序相反。

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="array--t"></a>array： t []

要以相反顺序复制其元素的数组。



## <a name="output--t"></a>输出： t []

包含元素的数组 `array[Length(array) - 1]` 。 `array[0]`.

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组元素的类型。