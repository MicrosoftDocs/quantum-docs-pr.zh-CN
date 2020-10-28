---
uid: Microsoft.Quantum.Canon.HY
title: 1XT-HY-UBW 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: bc3417ff948b718be5b96513f30f3e2714b9e20c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696050"
---
# <a name="hy-operation"></a><span data-ttu-id="d58e2-102">1XT-HY-UBW 操作</span><span class="sxs-lookup"><span data-stu-id="d58e2-102">HY operation</span></span>

<span data-ttu-id="d58e2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d58e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d58e2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d58e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d58e2-105">将 Y 基础模拟应用于交换 Z 轴和 Y 轴的 Hadamard 转换。</span><span class="sxs-lookup"><span data-stu-id="d58e2-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="d58e2-106">单个 qubit 上的 Y Hadamard 转换 $H _Y = S H $ 为：</span><span class="sxs-lookup"><span data-stu-id="d58e2-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="d58e2-107">\begin{align} H_Y \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="d58e2-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="d58e2-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="d58e2-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d58e2-109">输入</span><span class="sxs-lookup"><span data-stu-id="d58e2-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="d58e2-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d58e2-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d58e2-111">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="d58e2-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d58e2-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d58e2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d58e2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d58e2-113">See Also</span></span>

- [<span data-ttu-id="d58e2-114">Microsoft 量子。H</span><span class="sxs-lookup"><span data-stu-id="d58e2-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)