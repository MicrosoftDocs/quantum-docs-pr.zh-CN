---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855331"
---
# <a name="rmencoding-function"></a>RMEncoding 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1} 布尔值事实值的编码

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a>输入

### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

布尔值



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

如果为 false，则为 1; `b` 否则为-1