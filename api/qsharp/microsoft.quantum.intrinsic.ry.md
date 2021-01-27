---
uid: Microsoft.Quantum.Intrinsic.Ry
title: R 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: b50225b67701c6b17475445d5ed54400240e0b69
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818281"
---
# <a name="ry-operation"></a><span data-ttu-id="8d7c3-102">R 操作</span><span class="sxs-lookup"><span data-stu-id="8d7c3-102">Ry operation</span></span>

<span data-ttu-id="8d7c3-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="8d7c3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="8d7c3-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8d7c3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8d7c3-105">按给定角度向 $y $ 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="8d7c3-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="8d7c3-106">\begin{align} R_y ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos {2} \frac{\theta} \end{bmatrix}。  </span><span class="sxs-lookup"><span data-stu-id="8d7c3-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="8d7c3-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8d7c3-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8d7c3-108">输入</span><span class="sxs-lookup"><span data-stu-id="8d7c3-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="8d7c3-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8d7c3-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8d7c3-110">Qubit 要旋转的角度。</span><span class="sxs-lookup"><span data-stu-id="8d7c3-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="8d7c3-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8d7c3-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8d7c3-112">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="8d7c3-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d7c3-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d7c3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8d7c3-114">备注</span><span class="sxs-lookup"><span data-stu-id="8d7c3-114">Remarks</span></span>

<span data-ttu-id="8d7c3-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="8d7c3-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```