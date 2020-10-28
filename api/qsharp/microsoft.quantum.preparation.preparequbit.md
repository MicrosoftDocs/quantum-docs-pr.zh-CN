---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700433"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="664f5-102">PrepareQubit 操作</span><span class="sxs-lookup"><span data-stu-id="664f5-102">PrepareQubit operation</span></span>

<span data-ttu-id="664f5-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="664f5-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="664f5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="664f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="664f5-105">准备 + 1 (`Zero` 给定 Pauli 运算符) eigenstate 中的 qubit。</span><span class="sxs-lookup"><span data-stu-id="664f5-105">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="664f5-106">如果给定标识运算符，则 qubit 在最大化混合状态下准备就绪。</span><span class="sxs-lookup"><span data-stu-id="664f5-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="664f5-107">如果 qubit 最初处于 $ \ket {0} $ 状态，则此操作将在给定 Pauli 运算符的 $ + $1 eigenstate 中准备 qubit，或者，对于 `PauliI` 最大化 mixed 状态下的 (参阅 <xref:microsoft.quantum.preparation.preparesinglequbitidentity>) 。</span><span class="sxs-lookup"><span data-stu-id="664f5-107">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="664f5-108">如果 qubit 的状态不是 $ \ket {0} $，此操作将应用以下入口： $H $ for、 `PauliX` $HS $ for `PauliY` 、$I $ for `PauliZ` 和 <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` 。</span><span class="sxs-lookup"><span data-stu-id="664f5-108">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="664f5-109">输入</span><span class="sxs-lookup"><span data-stu-id="664f5-109">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="664f5-110">基础： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="664f5-110">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="664f5-111">Pauli 运算符 $P $。</span><span class="sxs-lookup"><span data-stu-id="664f5-111">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="664f5-112">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="664f5-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="664f5-113">要准备的 qubit。</span><span class="sxs-lookup"><span data-stu-id="664f5-113">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="664f5-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="664f5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

