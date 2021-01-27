---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: d46c42846066befafda2af22f7b6e861cb260c33
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831012"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="056fd-102">_flipToBasis 操作</span><span class="sxs-lookup"><span data-stu-id="056fd-102">_flipToBasis operation</span></span>

<span data-ttu-id="056fd-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="056fd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="056fd-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="056fd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="056fd-105">应用 unitaries，它将 $ \ket {0} \otimes\cdots\ket {0} $ 映射到 $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $，其中 $ \ket{\ psi_k} $ 依赖于 `basis[k]` 。</span><span class="sxs-lookup"><span data-stu-id="056fd-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="056fd-106">`basis[k]`和 $ \ket{\ psi_k} $ 的值之间的对应关系如下：</span><span class="sxs-lookup"><span data-stu-id="056fd-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="056fd-107">`basis[k]=0` $ \rightarrow \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="056fd-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="056fd-108">`basis[k]=1` $ \rightarrow \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="056fd-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="056fd-109">`basis[k]=2` $ \rightarrow \ket{+} $。</span><span class="sxs-lookup"><span data-stu-id="056fd-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="056fd-110">`basis[k]=3` $ \rightarrow \ket{i} $ ( + 1 eigenstate of Pauli Y ) 。</span><span class="sxs-lookup"><span data-stu-id="056fd-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="056fd-111">输入</span><span class="sxs-lookup"><span data-stu-id="056fd-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="056fd-112">basis： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="056fd-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="056fd-113">单 qubit 基础状态 Id (0 <= id 的数组 <= 3) ，每个 qubits 元素对应一个。</span><span class="sxs-lookup"><span data-stu-id="056fd-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="056fd-114">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="056fd-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="056fd-115">要操作的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="056fd-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="056fd-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="056fd-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

