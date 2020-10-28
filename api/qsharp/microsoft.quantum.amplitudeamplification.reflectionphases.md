---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700093"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="9611d-102">ReflectionPhases 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="9611d-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="9611d-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="9611d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="9611d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9611d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9611d-105">振幅放大中部分反射序列的阶段。</span><span class="sxs-lookup"><span data-stu-id="9611d-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="9611d-106">命名项</span><span class="sxs-lookup"><span data-stu-id="9611d-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="9611d-107">AboutStart： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9611d-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9611d-108">用于反射开始状态的阶段的数组。</span><span class="sxs-lookup"><span data-stu-id="9611d-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="9611d-109">AboutTarget： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9611d-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9611d-110">用于反射目标状态的阶段的数组。</span><span class="sxs-lookup"><span data-stu-id="9611d-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="9611d-111">注解</span><span class="sxs-lookup"><span data-stu-id="9611d-111">Remarks</span></span>

<span data-ttu-id="9611d-112">这两个数组的长度必须相等。</span><span class="sxs-lookup"><span data-stu-id="9611d-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="9611d-113">请注意，在许多情况下，有关目标状态的开始状态和最后一阶段的第一阶段会引入全局阶段转换，并可能设置为 $0 $。</span><span class="sxs-lookup"><span data-stu-id="9611d-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>