---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846248"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将映射和折叠合并为一个函数

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>说明

此函数 `fn` 通过数组来循环访问函数，从初始状态开始， `state` 返回所有中间值，不包括初始状态。

## <a name="input"></a>输入

### <a name="fn--statet---state"></a>fn： ( 状态，不) > "状态

要在数组上折叠的函数


### <a name="state--state"></a>状态： "状态"

要折叠的初始状态


### <a name="array--t"></a>array： t []

要折叠的值数组



## <a name="output--state"></a>输出： "State []

所有中间状态，包括最终状态，但不包括初始状态。
输出数组的长度与相同 `array` 。

## <a name="type-parameters"></a>类型参数

### <a name="state"></a>"状态

函数操作的状态的类型 `fn` ，即接受作为其第一个输入并返回。
### <a name="t"></a>找

元素的类型 `array` 。

## <a name="example"></a>示例

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```