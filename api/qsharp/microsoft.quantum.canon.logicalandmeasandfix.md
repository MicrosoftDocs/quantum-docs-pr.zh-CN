---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696019"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="8aa6d-102">LogicalANDMeasAndFix 操作</span><span class="sxs-lookup"><span data-stu-id="8aa6d-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="8aa6d-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8aa6d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8aa6d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8aa6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8aa6d-105">计算多个 qubits 的逻辑 AND。</span><span class="sxs-lookup"><span data-stu-id="8aa6d-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8aa6d-106">输入</span><span class="sxs-lookup"><span data-stu-id="8aa6d-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="8aa6d-107">ctrlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8aa6d-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8aa6d-108">Qubits 输入到多输入和入口。</span><span class="sxs-lookup"><span data-stu-id="8aa6d-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8aa6d-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8aa6d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8aa6d-110">要将和写入到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="8aa6d-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="8aa6d-111">假设此项始终以 $ \ket {0} $ 状态启动。</span><span class="sxs-lookup"><span data-stu-id="8aa6d-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8aa6d-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8aa6d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8aa6d-113">注解</span><span class="sxs-lookup"><span data-stu-id="8aa6d-113">Remarks</span></span>

<span data-ttu-id="8aa6d-114">当 `ctrlRegister` 正好为 $2 $ qubits 时，此项等效于操作，阶段为： $ `CCNOT` \ket {001} $ 和 $ \ket $ 上的 $ $ 和 $-e ^ {i \ pi/2} $ 上的阶段 $e ^ {i \ pi/2} $ {101} {011} 。</span><span class="sxs-lookup"><span data-stu-id="8aa6d-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="8aa6d-115">Adjoint 也是度量和修复方法，它仅在特殊情况下才是原始操作的逆操作 (参阅引用) ，但使用的 T-sql 更少。</span><span class="sxs-lookup"><span data-stu-id="8aa6d-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="8aa6d-116">参考</span><span class="sxs-lookup"><span data-stu-id="8aa6d-116">References</span></span>

- [<span data-ttu-id="8aa6d-117">*Craig Gidney* ，1709.06648</span><span class="sxs-lookup"><span data-stu-id="8aa6d-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)