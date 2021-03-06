---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833842"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="remarks"></a>备注

这主要用于将函数传递到需要操作作为输入的函数或操作。