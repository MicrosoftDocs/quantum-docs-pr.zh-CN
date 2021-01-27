---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: e6a88ccf4c01b2f0a7344e3823b2748790cf9650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854342"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="571ec-102">PrepareQubit 操作</span><span class="sxs-lookup"><span data-stu-id="571ec-102">PrepareQubit operation</span></span>

<span data-ttu-id="571ec-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="571ec-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="571ec-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="571ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="571ec-105">PrepareQubit 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="571ec-105">PrepareQubit has been deprecated.</span></span> <span data-ttu-id="571ec-106">请改用 <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate>。</span><span class="sxs-lookup"><span data-stu-id="571ec-106">Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.</span></span>

<span data-ttu-id="571ec-107">准备 + 1 (`Zero` 给定 Pauli 运算符) eigenstate 中的 qubit。</span><span class="sxs-lookup"><span data-stu-id="571ec-107">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="571ec-108">如果给定标识运算符，则 qubit 在最大化混合状态下准备就绪。</span><span class="sxs-lookup"><span data-stu-id="571ec-108">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="571ec-109">如果 qubit 最初处于 $ \ket {0} $ 状态，则此操作将在给定 Pauli 运算符的 $ + $1 eigenstate 中准备 qubit，或者，对于 `PauliI` 最大化 mixed 状态下的 (参阅 <xref:microsoft.quantum.preparation.preparesinglequbitidentity>) 。</span><span class="sxs-lookup"><span data-stu-id="571ec-109">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="571ec-110">如果 qubit 的状态不是 $ \ket {0} $，此操作将应用以下入口： $H $ for、 `PauliX` $HS $ for `PauliY` 、$I $ for `PauliZ` 和 <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` 。</span><span class="sxs-lookup"><span data-stu-id="571ec-110">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="571ec-111">输入</span><span class="sxs-lookup"><span data-stu-id="571ec-111">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="571ec-112">基础： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="571ec-112">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="571ec-113">Pauli 运算符 $P $。</span><span class="sxs-lookup"><span data-stu-id="571ec-113">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="571ec-114">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="571ec-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="571ec-115">要准备的 qubit。</span><span class="sxs-lookup"><span data-stu-id="571ec-115">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="571ec-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="571ec-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

