---
uid: Microsoft.Quantum.Arithmetic.Carry
title: 执行操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223589"
---
# <a name="carry-operation"></a><span data-ttu-id="75814-102">执行操作</span><span class="sxs-lookup"><span data-stu-id="75814-102">Carry operation</span></span>

<span data-ttu-id="75814-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="75814-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="75814-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75814-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75814-105">实现可逆的执行入口。</span><span class="sxs-lookup"><span data-stu-id="75814-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="75814-106">给定一个在 qubit 中进行编码的传入位， `carryIn` 并在和中编码两个被加数位， `summand1` 计算的 `summand2` 按位 xor `carryIn` ， `summand1` 并 `summand2` 在 qubit 中将 `summand2` 为 xored 到 qubit `carryOut` 。</span><span class="sxs-lookup"><span data-stu-id="75814-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="75814-107">输入</span><span class="sxs-lookup"><span data-stu-id="75814-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="75814-108">carryIn： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="75814-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="75814-109">传入的 qubit。</span><span class="sxs-lookup"><span data-stu-id="75814-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="75814-110">summand1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="75814-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="75814-111">第一个被加数 qubit。</span><span class="sxs-lookup"><span data-stu-id="75814-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="75814-112">summand2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="75814-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="75814-113">第二个被加数 qubit 被替换为与和之和的下 `summand1` 位 `summand2` 。</span><span class="sxs-lookup"><span data-stu-id="75814-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="75814-114">carryOut： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="75814-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="75814-115">执行 qubit 时，将 xored，并将其总和增加。</span><span class="sxs-lookup"><span data-stu-id="75814-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75814-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75814-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

