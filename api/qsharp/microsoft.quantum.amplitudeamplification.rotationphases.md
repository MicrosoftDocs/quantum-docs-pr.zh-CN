---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700080"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="aa0bc-102">RotationPhases 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="aa0bc-102">RotationPhases user defined type</span></span>

<span data-ttu-id="aa0bc-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="aa0bc-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="aa0bc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa0bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa0bc-105">振幅放大中 qubit 旋转序列的各个阶段。</span><span class="sxs-lookup"><span data-stu-id="aa0bc-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="aa0bc-106">注解</span><span class="sxs-lookup"><span data-stu-id="aa0bc-106">Remarks</span></span>

<span data-ttu-id="aa0bc-107">第一个参数是一个用于反射的阶段数组，表示为一个 qubit 旋转的积。</span><span class="sxs-lookup"><span data-stu-id="aa0bc-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="aa0bc-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-108">[ G.H.</span></span> <span data-ttu-id="aa0bc-109">低，I. L。</span><span class="sxs-lookup"><span data-stu-id="aa0bc-109">Low, I. L.</span></span> <span data-ttu-id="aa0bc-110">语， https://arxiv.org/abs/1707.05391 ]。</span><span class="sxs-lookup"><span data-stu-id="aa0bc-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>