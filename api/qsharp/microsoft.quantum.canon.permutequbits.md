---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852320"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="1fbbe-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="1fbbe-102">PermuteQubits operation</span></span>

<span data-ttu-id="1fbbe-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1fbbe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1fbbe-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1fbbe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1fbbe-105">使用交换操作 Permutes qubits。</span><span class="sxs-lookup"><span data-stu-id="1fbbe-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1fbbe-106">输入</span><span class="sxs-lookup"><span data-stu-id="1fbbe-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="1fbbe-107">排序： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1fbbe-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1fbbe-108">介绍 qubits 的新排序，其中，索引 i 处的 qubit 现在将按顺序 [i] 排序。</span><span class="sxs-lookup"><span data-stu-id="1fbbe-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="1fbbe-109">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1fbbe-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1fbbe-110">要对其进行操作的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="1fbbe-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1fbbe-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1fbbe-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="1fbbe-112">示例</span><span class="sxs-lookup"><span data-stu-id="1fbbe-112">Example</span></span>

<span data-ttu-id="1fbbe-113">给定顺序 = [2，1，0]，并注册 $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $，PermuteQubits 将寄存器更改为 $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $</span><span class="sxs-lookup"><span data-stu-id="1fbbe-113">Given ordering = [2, 1, 0] and register $\ket{\alpha_0} \ket{\alpha_1} \ket{\alpha_2}$, PermuteQubits changes the register into $\ket{\alpha_2} \ket{\alpha_1} \ket{\alpha_0}$</span></span>

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```