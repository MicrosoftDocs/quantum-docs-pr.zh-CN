---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845477"
---
# <a name="rest-function"></a>Rest 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


创建一个等于输入数组的数组，但第一个数组元素被删除。

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="array--t"></a>array： t []

一个数组，其第二个元素是要形成输出数组的第二个元素。



## <a name="output--t"></a>输出： t []

包含元素的数组 `array[1..Length(array) - 1]` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组元素的类型。