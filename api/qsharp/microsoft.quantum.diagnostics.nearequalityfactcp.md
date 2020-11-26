---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 95364541adfa1dc57b1f147c3992c9fd9f5f6c68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201557"
---
# <a name="nearequalityfactcp-function"></a>NearEqualityFactCP 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言传统复数的预期值为小公差 1e-10。

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a>输入

### <a name="actual--complexpolar"></a>实际： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

要检查的数字。


### <a name="expected--complexpolar"></a>应为： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

预期值。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

