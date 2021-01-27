---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854355"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="ff6ab-102">PreparePauliEigenstate 操作</span><span class="sxs-lookup"><span data-stu-id="ff6ab-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="ff6ab-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ff6ab-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ff6ab-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff6ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff6ab-105">准备给定 Pauli 运算符正 eigenstate 的 qubit。</span><span class="sxs-lookup"><span data-stu-id="ff6ab-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="ff6ab-106">如果给定标识运算符，则 qubit 在最大化混合状态下准备就绪。</span><span class="sxs-lookup"><span data-stu-id="ff6ab-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="ff6ab-107">说明</span><span class="sxs-lookup"><span data-stu-id="ff6ab-107">Description</span></span>

<span data-ttu-id="ff6ab-108">如果 qubit 最初处于 $ \ket {0} $ 状态，则此操作将在给定 Pauli 运算符的 $ + $1 eigenstate 中准备 qubit，或者，对于 `PauliI` 最大化 mixed 状态下的 (参阅 <xref:microsoft.quantum.preparation.preparesinglequbitidentity>) 。</span><span class="sxs-lookup"><span data-stu-id="ff6ab-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="ff6ab-109">如果 qubit 的状态不是 $ \ket {0} $，此操作将应用以下入口： $H $ for、 `PauliX` $HS $ for `PauliY` 、$I $ for `PauliZ` 和 <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` 。</span><span class="sxs-lookup"><span data-stu-id="ff6ab-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="ff6ab-110">输入</span><span class="sxs-lookup"><span data-stu-id="ff6ab-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="ff6ab-111">基础： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ff6ab-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ff6ab-112">Pauli 运算符 $P $。</span><span class="sxs-lookup"><span data-stu-id="ff6ab-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ff6ab-113">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff6ab-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff6ab-114">要准备的 qubit。</span><span class="sxs-lookup"><span data-stu-id="ff6ab-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff6ab-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff6ab-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="ff6ab-116">示例</span><span class="sxs-lookup"><span data-stu-id="ff6ab-116">Example</span></span>

<span data-ttu-id="ff6ab-117">准备 "$ \ket{+} $" 状态中的 qubit：</span><span class="sxs-lookup"><span data-stu-id="ff6ab-117">To prepare a qubit in the $\ket{+}$ state:</span></span>

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```