---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: e2d6e5a663f8c4e101c7e2ab1346d10cade3f4e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223453"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="f0517-102">CompareUsingRippleCarry 操作</span><span class="sxs-lookup"><span data-stu-id="f0517-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="f0517-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f0517-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f0517-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0517-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0517-105">此操作测试由 qubits 的寄存器表示的整数是否大于另一个整数，并将结果 XOR 应用到输出 qubit。</span><span class="sxs-lookup"><span data-stu-id="f0517-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f0517-106">描述</span><span class="sxs-lookup"><span data-stu-id="f0517-106">Description</span></span>

<span data-ttu-id="f0517-107">给定两个整数 `x` 并 `y` 存储在大小相等的 qubit 寄存器中，此操作将检查它们是否满足 `x > y` 。</span><span class="sxs-lookup"><span data-stu-id="f0517-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="f0517-108">如果为 true，则将 1 XORed 到输出 qubit。</span><span class="sxs-lookup"><span data-stu-id="f0517-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="f0517-109">否则，0将 XORed 到输出 qubit 中。</span><span class="sxs-lookup"><span data-stu-id="f0517-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="f0517-110">换句话说，此操作可由单一 $ $ \begin{align} U\ket {x} \ 票证 {y} \ 票证 {z} = \ket{x}\ket{y}\ket{z\oplus (x>y) } 表示。</span><span class="sxs-lookup"><span data-stu-id="f0517-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="f0517-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f0517-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f0517-112">输入</span><span class="sxs-lookup"><span data-stu-id="f0517-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="f0517-113">x： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f0517-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f0517-114">要进行比较的第一个数字以 `LittleEndian` qubit 寄存器格式存储。</span><span class="sxs-lookup"><span data-stu-id="f0517-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="f0517-115">y： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f0517-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f0517-116">要进行比较的第二个数字，以 `LittleEndian` qubit 寄存器格式存储。</span><span class="sxs-lookup"><span data-stu-id="f0517-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="f0517-117">输出： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f0517-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f0517-118">Qubit，用于存储比较 $x>y $ 的结果。</span><span class="sxs-lookup"><span data-stu-id="f0517-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0517-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0517-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f0517-120">参考</span><span class="sxs-lookup"><span data-stu-id="f0517-120">References</span></span>

- <span data-ttu-id="f0517-121">新的量程波纹-携带加法线路 Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="f0517-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>