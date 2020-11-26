---
uid: Microsoft.Quantum.Canon.HY
title: 1XT-HY-UBW 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: ceca8eab8cb8f16333cd7a1e3c24e6cebe4ec8d7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206827"
---
# <a name="hy-operation"></a><span data-ttu-id="e89e1-102">1XT-HY-UBW 操作</span><span class="sxs-lookup"><span data-stu-id="e89e1-102">HY operation</span></span>

<span data-ttu-id="e89e1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e89e1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e89e1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e89e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e89e1-105">将 Y 基础模拟应用于交换 Z 轴和 Y 轴的 Hadamard 转换。</span><span class="sxs-lookup"><span data-stu-id="e89e1-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="e89e1-106">单个 qubit 上的 Y Hadamard 转换 $H _Y = S H $ 为：</span><span class="sxs-lookup"><span data-stu-id="e89e1-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="e89e1-107">\begin{align} H_Y \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="e89e1-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="e89e1-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e89e1-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e89e1-109">输入</span><span class="sxs-lookup"><span data-stu-id="e89e1-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="e89e1-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e89e1-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e89e1-111">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="e89e1-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e89e1-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e89e1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e89e1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e89e1-113">See Also</span></span>

- [<span data-ttu-id="e89e1-114">Microsoft 量子。H</span><span class="sxs-lookup"><span data-stu-id="e89e1-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)