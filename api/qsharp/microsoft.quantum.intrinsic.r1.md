---
uid: Microsoft.Quantum.Intrinsic.R1
title: R1 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699800"
---
# <a name="r1-operation"></a><span data-ttu-id="b7f92-102">R1 操作</span><span class="sxs-lookup"><span data-stu-id="b7f92-102">R1 operation</span></span>

<span data-ttu-id="b7f92-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b7f92-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b7f92-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7f92-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7f92-105">{1}按给定角度对 $ \ket $ 状态应用旋转。</span><span class="sxs-lookup"><span data-stu-id="b7f92-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="b7f92-106">\begin{align} R_1 ( \theta) \mathrel{： =} \operatorname{diag} (1，e ^ {i\theta} ) 。</span><span class="sxs-lookup"><span data-stu-id="b7f92-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="b7f92-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b7f92-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b7f92-108">输入</span><span class="sxs-lookup"><span data-stu-id="b7f92-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="b7f92-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7f92-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7f92-110">Qubit 要旋转的角度。</span><span class="sxs-lookup"><span data-stu-id="b7f92-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="b7f92-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b7f92-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b7f92-112">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="b7f92-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7f92-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7f92-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b7f92-114">注解</span><span class="sxs-lookup"><span data-stu-id="b7f92-114">Remarks</span></span>

<span data-ttu-id="b7f92-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="b7f92-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```