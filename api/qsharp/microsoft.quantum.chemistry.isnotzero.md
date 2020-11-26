---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204056"
---
# <a name="isnotzero-function"></a>IsNotZero 函数

命名空间 [：](xref:Microsoft.Quantum.Chemistry)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


检查数字是否 `Double` 不约为零。

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>输入

### <a name="number--double"></a>number： [Double](xref:microsoft.quantum.lang-ref.double)

要检查的数字



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

如果 `number` 的绝对值大于，则返回 true `1e-15` 。