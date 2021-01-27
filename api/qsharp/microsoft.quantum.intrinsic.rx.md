---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Rx 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: b6224952ea5eabfc7177ead557378fb07b9e597f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849303"
---
# <a name="rx-operation"></a><span data-ttu-id="8ff1c-102">Rx 操作</span><span class="sxs-lookup"><span data-stu-id="8ff1c-102">Rx operation</span></span>

<span data-ttu-id="8ff1c-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="8ff1c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="8ff1c-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8ff1c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8ff1c-105">按给定角度向 $x $ 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="8ff1c-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="8ff1c-106">\begin{align} R_x ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-i\sin \frac{\theta} {2} \\ \\ -i\sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}。  </span><span class="sxs-lookup"><span data-stu-id="8ff1c-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="8ff1c-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8ff1c-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8ff1c-108">输入</span><span class="sxs-lookup"><span data-stu-id="8ff1c-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="8ff1c-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8ff1c-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8ff1c-110">Qubit 要旋转的角度。</span><span class="sxs-lookup"><span data-stu-id="8ff1c-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="8ff1c-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8ff1c-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8ff1c-112">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="8ff1c-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ff1c-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ff1c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8ff1c-114">备注</span><span class="sxs-lookup"><span data-stu-id="8ff1c-114">Remarks</span></span>

<span data-ttu-id="8ff1c-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="8ff1c-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```