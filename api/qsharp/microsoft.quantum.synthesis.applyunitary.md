---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859135"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="2b8ff-102">ApplyUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="2b8ff-102">ApplyUnitary operation</span></span>

<span data-ttu-id="2b8ff-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2b8ff-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2b8ff-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b8ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b8ff-105">应用由 2 ^ n x 2 ^ n 单一矩阵定义的门。</span><span class="sxs-lookup"><span data-stu-id="2b8ff-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="2b8ff-106">如果矩阵不是单一的或大小不正确，则会失败。</span><span class="sxs-lookup"><span data-stu-id="2b8ff-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2b8ff-107">输入</span><span class="sxs-lookup"><span data-stu-id="2b8ff-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="2b8ff-108">单一： [复杂](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="2b8ff-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="2b8ff-109">2 ^ n x 2 ^ n 单一矩阵，描述操作。</span><span class="sxs-lookup"><span data-stu-id="2b8ff-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="2b8ff-110">如果矩阵不是单一大小或不适合大小，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="2b8ff-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="2b8ff-111">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2b8ff-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2b8ff-112">应用长度为 n 的操作注册的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="2b8ff-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b8ff-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b8ff-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

