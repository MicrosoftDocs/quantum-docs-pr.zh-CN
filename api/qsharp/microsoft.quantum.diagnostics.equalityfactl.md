---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829146"
---
# <a name="equalityfactl-function"></a>EqualityFactL 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言传统 BigInt 变量具有预期值。

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--bigint"></a>实际： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要检查的数字。


### <a name="expected--bigint"></a>应为： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

预期值。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

触发断言时要使用的失败消息字符串。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

