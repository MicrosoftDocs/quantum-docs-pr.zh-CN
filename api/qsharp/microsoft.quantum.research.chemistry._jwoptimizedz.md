---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: e0b442a7ac237525acdc80e8e79044ebb523f8a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225901"
---
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="0f014-102">_JWOptimizedZ 操作</span><span class="sxs-lookup"><span data-stu-id="0f014-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="0f014-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0f014-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="0f014-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0f014-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="0f014-105">应用 Vny-rz-j42 旋转，在阶段估算中使用 C-NOT 技巧到双相位。</span><span class="sxs-lookup"><span data-stu-id="0f014-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0f014-106">输入</span><span class="sxs-lookup"><span data-stu-id="0f014-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="0f014-107">angle： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f014-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f014-108">旋转的 Vny-rz-j42 角度。</span><span class="sxs-lookup"><span data-stu-id="0f014-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="0f014-109">parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0f014-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0f014-110">Qubit，用于确定时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="0f014-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="0f014-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0f014-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="0f014-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f014-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

