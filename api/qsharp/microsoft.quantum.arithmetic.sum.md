---
uid: Microsoft.Quantum.Arithmetic.Sum
title: 操作总数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847757"
---
# <a name="sum-operation"></a><span data-ttu-id="0e1eb-102">操作总数</span><span class="sxs-lookup"><span data-stu-id="0e1eb-102">Sum operation</span></span>

<span data-ttu-id="0e1eb-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0e1eb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0e1eb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e1eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e1eb-105">实现可逆的 sum 入口。</span><span class="sxs-lookup"><span data-stu-id="0e1eb-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="0e1eb-106">给定一个以 qubit 编码的传入位 `carryIn` ，以及在和中编码的两个被加数位 `summand1` `summand2` ，计算的和的按位 xor `carryIn` `summand1` `summand2` `summand2` 。</span><span class="sxs-lookup"><span data-stu-id="0e1eb-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0e1eb-107">输入</span><span class="sxs-lookup"><span data-stu-id="0e1eb-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="0e1eb-108">carryIn： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0e1eb-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0e1eb-109">传入的 qubit。</span><span class="sxs-lookup"><span data-stu-id="0e1eb-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="0e1eb-110">summand1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0e1eb-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0e1eb-111">第一个被加数 qubit。</span><span class="sxs-lookup"><span data-stu-id="0e1eb-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="0e1eb-112">summand2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0e1eb-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0e1eb-113">第二个被加数 qubit 被替换为与和之和的下 `summand1` 位 `summand2` 。</span><span class="sxs-lookup"><span data-stu-id="0e1eb-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e1eb-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e1eb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0e1eb-115">备注</span><span class="sxs-lookup"><span data-stu-id="0e1eb-115">Remarks</span></span>

<span data-ttu-id="0e1eb-116">与 `Carry` 操作相反，此操作不会计算出执行位。</span><span class="sxs-lookup"><span data-stu-id="0e1eb-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>