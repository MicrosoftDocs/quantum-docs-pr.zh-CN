---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695674"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

软件包 [](https://nuget.org/packages/)


将函数转换为操作。

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>说明

给定函数后，将返回调用该函数的操作，该操作不执行任何其他操作。

## <a name="input"></a>输入

### <a name="fn--input---output"></a>fn： "输入 >" 输出

要转换为操作的函数。



## <a name="output--input--output"></a>输出： "Input =>" 输出 

与 `op` `op(input)` 所有相同的操作 `fn(input)` `input` 。

## <a name="type-parameters"></a>类型参数

### <a name="input"></a>' 输入

要转换的函数的输入类型。
### <a name="output"></a>' Output

要转换的函数的输出类型。

## <a name="remarks"></a>注解

这主要用于将函数传递到需要操作作为输入的函数或操作。