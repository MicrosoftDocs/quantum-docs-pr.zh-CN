---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843965"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="f1c48-102">RotationPhases 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="f1c48-102">RotationPhases user defined type</span></span>

<span data-ttu-id="f1c48-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="f1c48-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="f1c48-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1c48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1c48-105">振幅放大中 qubit 旋转序列的各个阶段。</span><span class="sxs-lookup"><span data-stu-id="f1c48-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="f1c48-106">备注</span><span class="sxs-lookup"><span data-stu-id="f1c48-106">Remarks</span></span>

<span data-ttu-id="f1c48-107">第一个参数是一个用于反射的阶段数组，表示为一个 qubit 旋转的积。</span><span class="sxs-lookup"><span data-stu-id="f1c48-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="f1c48-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="f1c48-108">[ G.H.</span></span> <span data-ttu-id="f1c48-109">低，I. L。</span><span class="sxs-lookup"><span data-stu-id="f1c48-109">Low, I. L.</span></span> <span data-ttu-id="f1c48-110">语， https://arxiv.org/abs/1707.05391 ]。</span><span class="sxs-lookup"><span data-stu-id="f1c48-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>