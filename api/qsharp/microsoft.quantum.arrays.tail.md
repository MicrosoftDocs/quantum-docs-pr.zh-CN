---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845408"
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