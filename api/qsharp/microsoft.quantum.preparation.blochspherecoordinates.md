---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 594896a72fe40e5ba994e08500c3ce71b185bfff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193550"
---
# <a name="blochspherecoordinates-function"></a><span data-ttu-id="f4e78-102">BlochSphereCoordinates 函数</span><span class="sxs-lookup"><span data-stu-id="f4e78-102">BlochSphereCoordinates function</span></span>

<span data-ttu-id="f4e78-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f4e78-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f4e78-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4e78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4e78-105">计算单一 qubit 状态的 Bloch 球体坐标。</span><span class="sxs-lookup"><span data-stu-id="f4e78-105">Computes the Bloch sphere coordinates for a single-qubit state.</span></span>

<span data-ttu-id="f4e78-106">假设有两个复数 $a 0，a1 $，表示 qubit 状态，计算 Bloch 球上的坐标，使 $a 0 \ket {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i \phi/2}\cos{ ( \ theta/2) } \ket {0} + e ^ {i \phi/2}\sin{ ( \ theta/2) } \ket {1}) $。</span><span class="sxs-lookup"><span data-stu-id="f4e78-106">Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.</span></span>

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a><span data-ttu-id="f4e78-107">输入</span><span class="sxs-lookup"><span data-stu-id="f4e78-107">Input</span></span>

### <a name="a0--complexpolar"></a><span data-ttu-id="f4e78-108">a0： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f4e78-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f4e78-109">状态 $ \ket $ 的复杂系数 {0} 。</span><span class="sxs-lookup"><span data-stu-id="f4e78-109">Complex coefficient of state $\ket{0}$.</span></span>


### <a name="a1--complexpolar"></a><span data-ttu-id="f4e78-110">a1： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f4e78-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f4e78-111">状态 $ \ket $ 的复杂系数 {1} 。</span><span class="sxs-lookup"><span data-stu-id="f4e78-111">Complex coefficient of state $\ket{1}$.</span></span>



## <a name="output--complexpolardoubledouble"></a><span data-ttu-id="f4e78-112">Output： ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)、[double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double)) </span><span class="sxs-lookup"><span data-stu-id="f4e78-112">Output : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="f4e78-113">包含的元组 `(ComplexPolar(r, t), phi, theta)` 。</span><span class="sxs-lookup"><span data-stu-id="f4e78-113">A tuple containing `(ComplexPolar(r, t), phi, theta)`.</span></span>