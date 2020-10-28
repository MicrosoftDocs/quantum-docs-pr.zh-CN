---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 1d62d25a3d04c431440cf8fc1eb585cac2c73f2e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695552"
---
# <a name="nearequalityfactcp-function"></a>NearEqualityFactCP 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

软件包 [](https://nuget.org/packages/)


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

