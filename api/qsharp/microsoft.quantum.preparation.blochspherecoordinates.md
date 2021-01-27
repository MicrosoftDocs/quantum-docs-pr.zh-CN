---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 62643f64a6b829949fa708e300d9d262527dbb29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855897"
---
# <a name="blochspherecoordinates-function"></a>BlochSphereCoordinates 函数

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


计算单一 qubit 状态的 Bloch 球体坐标。

假设有两个复数 $a 0，a1 $，表示 qubit 状态，计算 Bloch 球上的坐标，使 $a 0 \ket {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i \phi/2}\cos{ ( \ theta/2) } \ket {0} + e ^ {i \phi/2}\sin{ ( \ theta/2) } \ket {1}) $。

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a>输入

### <a name="a0--complexpolar"></a>a0： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

状态 $ \ket $ 的复杂系数 {0} 。


### <a name="a1--complexpolar"></a>a1： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

状态 $ \ket $ 的复杂系数 {1} 。



## <a name="output--complexpolardoubledouble"></a>Output： ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)、[double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double)) 

包含的元组 `(ComplexPolar(r, t), phi, theta)` 。