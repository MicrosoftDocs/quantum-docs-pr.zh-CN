---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218795"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="8201f-102">ApplyFermionicSWAP 操作</span><span class="sxs-lookup"><span data-stu-id="8201f-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="8201f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8201f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8201f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8201f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8201f-105">应用 Fermionic 交换。</span><span class="sxs-lookup"><span data-stu-id="8201f-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8201f-106">描述</span><span class="sxs-lookup"><span data-stu-id="8201f-106">Description</span></span>

<span data-ttu-id="8201f-107">如果两个 qubits 都是1，则这实质上是交换 qubits，同时应用-1 的全局阶段。</span><span class="sxs-lookup"><span data-stu-id="8201f-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="8201f-108">保留 orbitals 的 symmetrization。</span><span class="sxs-lookup"><span data-stu-id="8201f-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="8201f-109">有关详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="8201f-109">See  for more information.</span></span>

<span data-ttu-id="8201f-110">此操作由单一运算符 \begin{align} f_ {swap} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="8201f-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="8201f-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8201f-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="8201f-112">输入</span><span class="sxs-lookup"><span data-stu-id="8201f-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="8201f-113">qubit1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8201f-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8201f-114">要交换的第一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="8201f-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="8201f-115">qubit2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8201f-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8201f-116">要交换的第二个 qubit。</span><span class="sxs-lookup"><span data-stu-id="8201f-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8201f-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8201f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="8201f-118">参考</span><span class="sxs-lookup"><span data-stu-id="8201f-118">References</span></span>

- [<span data-ttu-id="8201f-119">*Ryan Babbush、Nathan Wiebe、Jarrod McClean、James McClain、Hartmut Neven、Garnet Kin-Lic 更改*、arXiv：1706.00023</span><span class="sxs-lookup"><span data-stu-id="8201f-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="8201f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8201f-120">See Also</span></span>

- [<span data-ttu-id="8201f-121">。交换</span><span class="sxs-lookup"><span data-stu-id="8201f-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)