---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 8bbd4af0389a7b748be11dc50bacd2c178521adc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700897"
---
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="f8f78-102">_JWOptimizedZ 操作</span><span class="sxs-lookup"><span data-stu-id="f8f78-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="f8f78-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f8f78-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f8f78-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8f78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8f78-105">应用 Vny-rz-j42 旋转，在阶段估算中使用 C-NOT 技巧到双相位。</span><span class="sxs-lookup"><span data-stu-id="f8f78-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f8f78-106">输入</span><span class="sxs-lookup"><span data-stu-id="f8f78-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="f8f78-107">angle： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f8f78-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f8f78-108">旋转的 Vny-rz-j42 角度。</span><span class="sxs-lookup"><span data-stu-id="f8f78-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="f8f78-109">parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f8f78-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f8f78-110">Qubit，用于确定时间演化的符号。</span><span class="sxs-lookup"><span data-stu-id="f8f78-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="f8f78-111">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f8f78-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="f8f78-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8f78-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

