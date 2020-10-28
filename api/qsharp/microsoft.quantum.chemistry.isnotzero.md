---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695862"
---
# <a name="isnotzero-function"></a>IsNotZero 函数

命名空间 [：](xref:Microsoft.Quantum.Chemistry)

软件包 [](https://nuget.org/packages/)


检查数字是否 `Double` 不约为零。

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>输入

### <a name="number--double"></a>number： [Double](xref:microsoft.quantum.lang-ref.double)

要检查的数字



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

如果 `number` 的绝对值大于，则返回 true `1e-15` 。