---
uid: Microsoft.Quantum.Convert.Call
title: 调用操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214205"
---
# <a name="call-operation"></a>调用操作

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


调用具有给定输入的函数。

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>描述

给定函数和该函数的输入时，将调用函数并返回其输出。

## <a name="input"></a>输入

### <a name="fn--input---output"></a>fn： "输入 >" 输出

要调用的函数。


### <a name="input--input"></a>输入： "输入

要传递给函数的输入。



## <a name="output--output"></a>Output： "Output

调用 `fn` 的结果。

## <a name="type-parameters"></a>类型参数

### <a name="input"></a>' 输入


### <a name="output"></a>' Output



## <a name="remarks"></a>备注

此操作主要适用于强制在操作内的特定位置调用函数，或用于调用应执行操作的函数。