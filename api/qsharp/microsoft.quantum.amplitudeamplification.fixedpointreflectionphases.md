---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700105"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="5c308-102">FixedPointReflectionPhases 函数</span><span class="sxs-lookup"><span data-stu-id="5c308-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="5c308-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5c308-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5c308-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c308-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c308-105">计算固定点幅度放大的部分反射阶段。</span><span class="sxs-lookup"><span data-stu-id="5c308-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="5c308-106">输入</span><span class="sxs-lookup"><span data-stu-id="5c308-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="5c308-107">nQueries： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c308-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c308-108">Oracle 状态准备的查询数。</span><span class="sxs-lookup"><span data-stu-id="5c308-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="5c308-109">必须是奇整数。</span><span class="sxs-lookup"><span data-stu-id="5c308-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="5c308-110">successMin： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5c308-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5c308-111">最小成功概率。</span><span class="sxs-lookup"><span data-stu-id="5c308-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="5c308-112">输出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="5c308-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="5c308-113">可在定点波幅放大量程算法实现中使用的阶段数组。</span><span class="sxs-lookup"><span data-stu-id="5c308-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="5c308-114">参考</span><span class="sxs-lookup"><span data-stu-id="5c308-114">References</span></span>

<span data-ttu-id="5c308-115">我们使用 "使用最佳查询数进行定点的固定点放大" 中的阶段</span><span class="sxs-lookup"><span data-stu-id="5c308-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="5c308-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) 另请参阅 "复合量程入口方法"</span><span class="sxs-lookup"><span data-stu-id="5c308-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="5c308-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) 的 `RotationPhases` 格式为。</span><span class="sxs-lookup"><span data-stu-id="5c308-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>