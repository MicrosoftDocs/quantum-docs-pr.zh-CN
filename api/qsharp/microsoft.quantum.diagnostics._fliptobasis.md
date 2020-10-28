---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: e074ed2ae259f6aef49a8d327ce518a9e2caebfa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695622"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="2b2c3-102">_flipToBasis 操作</span><span class="sxs-lookup"><span data-stu-id="2b2c3-102">_flipToBasis operation</span></span>

<span data-ttu-id="2b2c3-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2b2c3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2b2c3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b2c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b2c3-105">应用 unitaries，它将 $ \ket {0} \otimes\cdots\ket {0} $ 映射到 $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $，其中 $ \ket{\ psi_k} $ 依赖于 `basis[k]` 。</span><span class="sxs-lookup"><span data-stu-id="2b2c3-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="2b2c3-106">`basis[k]`和 $ \ket{\ psi_k} $ 的值之间的对应关系如下：</span><span class="sxs-lookup"><span data-stu-id="2b2c3-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="2b2c3-107">`basis[k]=0` $ \rightarrow \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="2b2c3-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="2b2c3-108">`basis[k]=1` $ \rightarrow \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="2b2c3-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="2b2c3-109">`basis[k]=2` $ \rightarrow \ket{+} $。</span><span class="sxs-lookup"><span data-stu-id="2b2c3-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="2b2c3-110">`basis[k]=3` $ \rightarrow \ket{i} $ ( + 1 eigenstate of Pauli Y ) 。</span><span class="sxs-lookup"><span data-stu-id="2b2c3-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2b2c3-111">输入</span><span class="sxs-lookup"><span data-stu-id="2b2c3-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="2b2c3-112">basis： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2b2c3-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2b2c3-113">单 qubit 基础状态 Id (0 <= id 的数组 <= 3) ，每个 qubits 元素对应一个。</span><span class="sxs-lookup"><span data-stu-id="2b2c3-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2b2c3-114">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2b2c3-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2b2c3-115">要操作的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="2b2c3-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b2c3-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b2c3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

