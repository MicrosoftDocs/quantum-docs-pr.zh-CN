---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695555"
---
# <a name="formattedfailure-function"></a>FormattedFailure 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

软件包 [](https://nuget.org/packages/)


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



## <a name="remarks"></a>注解

此函数旨在由模拟运行时进行模拟，以便允许格式矛盾转发。