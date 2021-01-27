---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839600"
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