---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: ef9be0f0628c8ba8c5f131cc558bdcda6bb6ea55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701140"
---
# <a name="rmencoding-function"></a>RMEncoding 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


{-1,1} 布尔值事实值的编码

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a>输入

### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

布尔值



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

如果为 false，则为 1; `b` 否则为-1