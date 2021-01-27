---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845054"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="ed262-102">ApplyFermionicSWAP 操作</span><span class="sxs-lookup"><span data-stu-id="ed262-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="ed262-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ed262-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ed262-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed262-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed262-105">应用 Fermionic 交换。</span><span class="sxs-lookup"><span data-stu-id="ed262-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ed262-106">说明</span><span class="sxs-lookup"><span data-stu-id="ed262-106">Description</span></span>

<span data-ttu-id="ed262-107">如果两个 qubits 都是1，则这实质上是交换 qubits，同时应用-1 的全局阶段。</span><span class="sxs-lookup"><span data-stu-id="ed262-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="ed262-108">保留 orbitals 的 symmetrization。</span><span class="sxs-lookup"><span data-stu-id="ed262-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="ed262-109">有关详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="ed262-109">See  for more information.</span></span>

<span data-ttu-id="ed262-110">此操作由单一运算符 \begin{align} f_ {swap} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="ed262-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="ed262-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ed262-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="ed262-112">输入</span><span class="sxs-lookup"><span data-stu-id="ed262-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="ed262-113">qubit1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ed262-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ed262-114">要交换的第一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="ed262-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="ed262-115">qubit2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ed262-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ed262-116">要交换的第二个 qubit。</span><span class="sxs-lookup"><span data-stu-id="ed262-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ed262-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed262-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="ed262-118">参考</span><span class="sxs-lookup"><span data-stu-id="ed262-118">References</span></span>

- [<span data-ttu-id="ed262-119">*Ryan Babbush、Nathan Wiebe、Jarrod McClean、James McClain、Hartmut Neven、Garnet Kin-Lic 更改*、arXiv：1706.00023</span><span class="sxs-lookup"><span data-stu-id="ed262-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="ed262-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed262-120">See Also</span></span>

- [<span data-ttu-id="ed262-121">。交换</span><span class="sxs-lookup"><span data-stu-id="ed262-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)