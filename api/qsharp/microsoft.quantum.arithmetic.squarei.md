---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696567"
---
# <a name="squarei-operation"></a><span data-ttu-id="6fa3a-102">SquareI 操作</span><span class="sxs-lookup"><span data-stu-id="6fa3a-102">SquareI operation</span></span>

<span data-ttu-id="6fa3a-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6fa3a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6fa3a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6fa3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6fa3a-105">将整数的平方计算 `xs` 为 `result` ，其最初必须为零。</span><span class="sxs-lookup"><span data-stu-id="6fa3a-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6fa3a-106">输入</span><span class="sxs-lookup"><span data-stu-id="6fa3a-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="6fa3a-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6fa3a-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6fa3a-108">$n $ bit (LittleEndian) </span><span class="sxs-lookup"><span data-stu-id="6fa3a-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="6fa3a-109">result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6fa3a-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6fa3a-110">$ 2n $-bit result (LittleEndian) ，其最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="6fa3a-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6fa3a-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fa3a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6fa3a-112">注解</span><span class="sxs-lookup"><span data-stu-id="6fa3a-112">Remarks</span></span>

<span data-ttu-id="6fa3a-113">使用标准的移位和添加方法计算正方形。</span><span class="sxs-lookup"><span data-stu-id="6fa3a-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="6fa3a-114">与直向前解决方案节省 $n-$1 qubits，此解决方案先复制 x，然后应用常规乘数，然后撤消复制操作。</span><span class="sxs-lookup"><span data-stu-id="6fa3a-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>