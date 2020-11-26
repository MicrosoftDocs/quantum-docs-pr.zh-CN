---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: a506ccb637b331a392ea75383c8bd605114af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202934"
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