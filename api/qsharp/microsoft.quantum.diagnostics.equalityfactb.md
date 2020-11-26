---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201914"
---
# <a name="equalityfactb-function"></a>EqualityFactB 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言传统 Bool 变量具有预期值。

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--bool"></a>实际： [Bool](xref:microsoft.quantum.lang-ref.bool)

要检查的变量。


### <a name="expected--bool"></a>应为： [Bool](xref:microsoft.quantum.lang-ref.bool)

预期值。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

触发断言时要使用的失败消息字符串。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

