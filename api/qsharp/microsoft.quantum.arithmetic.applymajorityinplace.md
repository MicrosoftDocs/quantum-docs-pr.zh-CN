---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843729"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="a1093-102">ApplyMajorityInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="a1093-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="a1093-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a1093-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a1093-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1093-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1093-105">在 qubits 的收银机上就地应用三个 qubit 多数操作。</span><span class="sxs-lookup"><span data-stu-id="a1093-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a1093-106">说明</span><span class="sxs-lookup"><span data-stu-id="a1093-106">Description</span></span>

<span data-ttu-id="a1093-107">此操作计算 3 qubits 上就地的函数。</span><span class="sxs-lookup"><span data-stu-id="a1093-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="a1093-108">如果我们将 output qubit 表示为 $z $ 和输入 qubits 作为 $x $ 和 $y $，则该操作将执行以下转换： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x，y，z) } $。</span><span class="sxs-lookup"><span data-stu-id="a1093-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="a1093-109">输入</span><span class="sxs-lookup"><span data-stu-id="a1093-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="a1093-110">输出： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a1093-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a1093-111">第一个输入 qubit。</span><span class="sxs-lookup"><span data-stu-id="a1093-111">First input qubit.</span></span> <span data-ttu-id="a1093-112">请注意，输出是就地计算的，并存储在此 qubit 中。</span><span class="sxs-lookup"><span data-stu-id="a1093-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="a1093-113">输入： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a1093-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a1093-114">第二个和第三个输入 qubits。</span><span class="sxs-lookup"><span data-stu-id="a1093-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1093-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1093-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

