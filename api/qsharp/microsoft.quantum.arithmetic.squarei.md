---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 6813c8144b0ac98bae404b5e9b97e08b06c6bb3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846317"
---
# <a name="squarei-operation"></a><span data-ttu-id="7a30a-102">SquareI 操作</span><span class="sxs-lookup"><span data-stu-id="7a30a-102">SquareI operation</span></span>

<span data-ttu-id="7a30a-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7a30a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7a30a-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7a30a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7a30a-105">将整数的平方计算 `xs` 为 `result` ，其最初必须为零。</span><span class="sxs-lookup"><span data-stu-id="7a30a-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7a30a-106">输入</span><span class="sxs-lookup"><span data-stu-id="7a30a-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7a30a-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7a30a-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7a30a-108">$n $ bit (LittleEndian) </span><span class="sxs-lookup"><span data-stu-id="7a30a-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="7a30a-109">result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7a30a-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7a30a-110">$ 2n $-bit result (LittleEndian) ，其最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="7a30a-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a30a-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a30a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7a30a-112">备注</span><span class="sxs-lookup"><span data-stu-id="7a30a-112">Remarks</span></span>

<span data-ttu-id="7a30a-113">使用标准的移位和添加方法计算正方形。</span><span class="sxs-lookup"><span data-stu-id="7a30a-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="7a30a-114">与直向前解决方案节省 $n-$1 qubits，此解决方案先复制 x，然后应用常规乘数，然后撤消复制操作。</span><span class="sxs-lookup"><span data-stu-id="7a30a-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>