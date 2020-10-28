---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Vny-rz-j42 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699781"
---
# <a name="rz-operation"></a><span data-ttu-id="2dac5-102">Vny-rz-j42 操作</span><span class="sxs-lookup"><span data-stu-id="2dac5-102">Rz operation</span></span>

<span data-ttu-id="2dac5-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2dac5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2dac5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2dac5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2dac5-105">按给定角度向 $z $ 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="2dac5-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="2dac5-106">\begin{align} R_z ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="2dac5-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="2dac5-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2dac5-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2dac5-108">输入</span><span class="sxs-lookup"><span data-stu-id="2dac5-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="2dac5-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2dac5-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2dac5-110">Qubit 要旋转的角度。</span><span class="sxs-lookup"><span data-stu-id="2dac5-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="2dac5-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2dac5-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2dac5-112">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="2dac5-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2dac5-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2dac5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2dac5-114">注解</span><span class="sxs-lookup"><span data-stu-id="2dac5-114">Remarks</span></span>

<span data-ttu-id="2dac5-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="2dac5-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```