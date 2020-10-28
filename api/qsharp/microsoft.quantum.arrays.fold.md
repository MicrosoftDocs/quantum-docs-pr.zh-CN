---
uid: Microsoft.Quantum.Arrays.Fold
title: 折页函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696512"
---
# <a name="fold-function"></a>折页函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


通过数组循环访问函数 `f` `array` ，返回 `f(f(f(initialState, array[0]), array[1]), ...)` 。

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>输入

### <a name="folder--statet---state"></a>文件夹： ( "状态，不) ->" 状态

要在数组上折叠的函数。


### <a name="state--state"></a>状态： "状态"

文件夹的初始状态。


### <a name="array--t"></a>array： t []

要折叠的值的数组。



## <a name="output--state"></a>输出： "状态

遍历的所有元素后，文件夹返回的最终状态 `array` 。

## <a name="type-parameters"></a>类型参数

### <a name="state"></a>"状态

函数操作的状态的类型 `folder` ，即接受作为其第一个参数，并返回。
### <a name="t"></a>找

元素的类型 `array` 。