---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反转函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845455"
---
# <a name="reversed-function"></a>反转函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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