---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828279"
---
# <a name="formattedfailure-function"></a>FormattedFailure 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


用于在出现有意义的错误消息时失败的内部函数。

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--t"></a>实际：不




### <a name="expected--t"></a>应为： t




### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

此函数旨在由模拟运行时进行模拟，以便允许格式矛盾转发。