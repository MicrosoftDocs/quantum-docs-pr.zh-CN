---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191187"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="b1294-102">RotationPhasesAsReflectionPhases 函数</span><span class="sxs-lookup"><span data-stu-id="b1294-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="b1294-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b1294-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b1294-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1294-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1294-105">将指定为单一 qubit 旋转的阶段转换为指定为部分反射的阶段。</span><span class="sxs-lookup"><span data-stu-id="b1294-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="b1294-106">输入</span><span class="sxs-lookup"><span data-stu-id="b1294-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="b1294-107">rotPhases： [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="b1294-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="b1294-108">要转换为部分反射的 qubit 旋转的数组。</span><span class="sxs-lookup"><span data-stu-id="b1294-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="b1294-109">输出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="b1294-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="b1294-110">用于实现指定为部分反射的阶段的操作。</span><span class="sxs-lookup"><span data-stu-id="b1294-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="b1294-111">参考</span><span class="sxs-lookup"><span data-stu-id="b1294-111">References</span></span>

<span data-ttu-id="b1294-112">我们使用中的约定</span><span class="sxs-lookup"><span data-stu-id="b1294-112">We use the convention in</span></span>

- <span data-ttu-id="b1294-113">[ *G.H. Low，语*](https://arxiv.org/abs/1707.05391)将 qubit 循环阶段与反射运算符阶段相关联。</span><span class="sxs-lookup"><span data-stu-id="b1294-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>