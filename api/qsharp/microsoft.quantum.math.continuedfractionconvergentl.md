---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: a02b38fedb5b0025f04e7bba86f2f998493206b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700668"
---
# <a name="continuedfractionconvergentl-function"></a>ContinuedFractionConvergentL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


查找最接近于 `fraction` 分母小于或等于的连续分数收敛性 `denominatorBound`

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a>输入

### <a name="fraction--bigfraction"></a>分数： [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)




### <a name="denominatorbound--bigint"></a>denominatorBound： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigfraction"></a>输出： [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)

最接近的分数， `fraction` 分母小于或等于 `denominatorBound`