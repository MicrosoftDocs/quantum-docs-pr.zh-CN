---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695551"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

软件包 [](https://nuget.org/packages/)


断言传统浮点值的预期值为小公差 1e-10。

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>输入

### <a name="actual--double"></a>实际： [Double](xref:microsoft.quantum.lang-ref.double)

要检查的数字。


### <a name="expected--double"></a>应为： [Double](xref:microsoft.quantum.lang-ref.double)

预期值。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

这等效于 <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> 带有硬编码容差 $10 ^ {-10} $ 的。