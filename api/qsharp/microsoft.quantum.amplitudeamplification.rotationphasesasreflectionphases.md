---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700076"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="5f5a0-102">RotationPhasesAsReflectionPhases 函数</span><span class="sxs-lookup"><span data-stu-id="5f5a0-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="5f5a0-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5f5a0-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5f5a0-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5f5a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5f5a0-105">将指定为单一 qubit 旋转的阶段转换为指定为部分反射的阶段。</span><span class="sxs-lookup"><span data-stu-id="5f5a0-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="5f5a0-106">输入</span><span class="sxs-lookup"><span data-stu-id="5f5a0-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="5f5a0-107">rotPhases： [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="5f5a0-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="5f5a0-108">要转换为部分反射的 qubit 旋转的数组。</span><span class="sxs-lookup"><span data-stu-id="5f5a0-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="5f5a0-109">输出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="5f5a0-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="5f5a0-110">用于实现指定为部分反射的阶段的操作。</span><span class="sxs-lookup"><span data-stu-id="5f5a0-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="5f5a0-111">参考</span><span class="sxs-lookup"><span data-stu-id="5f5a0-111">References</span></span>

<span data-ttu-id="5f5a0-112">我们使用中的约定</span><span class="sxs-lookup"><span data-stu-id="5f5a0-112">We use the convention in</span></span>

- <span data-ttu-id="5f5a0-113">[ *G.H. Low，语*](https://arxiv.org/abs/1707.05391)将 qubit 循环阶段与反射运算符阶段相关联。</span><span class="sxs-lookup"><span data-stu-id="5f5a0-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>