---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191357"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="52b6c-102">RotationPhases 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="52b6c-102">RotationPhases user defined type</span></span>

<span data-ttu-id="52b6c-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="52b6c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="52b6c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52b6c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52b6c-105">振幅放大中 qubit 旋转序列的各个阶段。</span><span class="sxs-lookup"><span data-stu-id="52b6c-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="52b6c-106">备注</span><span class="sxs-lookup"><span data-stu-id="52b6c-106">Remarks</span></span>

<span data-ttu-id="52b6c-107">第一个参数是一个用于反射的阶段数组，表示为一个 qubit 旋转的积。</span><span class="sxs-lookup"><span data-stu-id="52b6c-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="52b6c-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="52b6c-108">[ G.H.</span></span> <span data-ttu-id="52b6c-109">低，I. L。</span><span class="sxs-lookup"><span data-stu-id="52b6c-109">Low, I. L.</span></span> <span data-ttu-id="52b6c-110">语， https://arxiv.org/abs/1707.05391 ]。</span><span class="sxs-lookup"><span data-stu-id="52b6c-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>