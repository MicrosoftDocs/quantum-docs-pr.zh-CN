---
uid: Microsoft.Quantum.Logical.Conditioned
title: 可调函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198480"
---
# <a name="conditioned-function"></a>可调函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


根据布尔条件的值返回两个值中的一个值。

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>输入

### <a name="condition--bool"></a>condition： [Bool](xref:microsoft.quantum.lang-ref.bool)

用于控制返回的输入的条件。


### <a name="iftrue--t"></a>ifTrue： t

当为时要返回的 `condition` 值 `true` 。


### <a name="iffalse--t"></a>ifFalse： t

当为时要返回的 `condition` 值 `false` 。



## <a name="output--t"></a>输出：不

`ifTrue` 如果 `condition` 为，则为; `true` `ifFalse` 否则为。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

与 `?|` 运算符不同，此函数不会进行短路，因此，这两个输入都是完全计算的。

最多短路行为，如下所示：

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```