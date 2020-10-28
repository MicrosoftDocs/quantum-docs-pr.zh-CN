---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696447"
---
# <a name="tail-function"></a>Tail 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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