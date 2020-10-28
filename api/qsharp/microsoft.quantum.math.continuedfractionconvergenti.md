---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 2322e005a5afb73d9719eb65d9ebf50740f1c9fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700484"
---
# <a name="continuedfractionconvergenti-function"></a>ContinuedFractionConvergentI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


查找最接近于 `fraction` 分母小于或等于的连续分数收敛性 `denominatorBound`

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a>输入

### <a name="fraction--fraction"></a>分式： [分数](xref:Microsoft.Quantum.Math.Fraction)




### <a name="denominatorbound--int"></a>denominatorBound： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--fraction"></a>输出： [分数](xref:Microsoft.Quantum.Math.Fraction)

最接近的分数， `fraction` 分母小于或等于 `denominatorBound`