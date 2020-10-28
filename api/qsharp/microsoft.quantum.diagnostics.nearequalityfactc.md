---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactC
title: NearEqualityFactC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactC
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: aef4925452fe2de444b1995f92b8fe1a2894834a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695553"
---
# <a name="nearequalityfactc-function"></a>NearEqualityFactC 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

软件包 [](https://nuget.org/packages/)


断言传统复数的预期值为小公差 1e-10。

```qsharp
function NearEqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex) : Unit
```


## <a name="input"></a>输入

### <a name="actual--complex"></a>实际： [复杂](xref:Microsoft.Quantum.Math.Complex)

要检查的数字。


### <a name="expected--complex"></a>应为： [复杂](xref:Microsoft.Quantum.Math.Complex)

预期值。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

