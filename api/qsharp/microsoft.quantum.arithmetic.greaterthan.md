---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699872"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="81566-102">GreaterThan 操作</span><span class="sxs-lookup"><span data-stu-id="81566-102">GreaterThan operation</span></span>

<span data-ttu-id="81566-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="81566-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="81566-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81566-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81566-105">对编码到 qubit 寄存器中的两个整数应用大于比较，并根据比较结果翻转目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="81566-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="81566-106">说明</span><span class="sxs-lookup"><span data-stu-id="81566-106">Description</span></span>

<span data-ttu-id="81566-107">严格大于比较两个整数 $x $ 和 $y $，并以 qubit 寄存器 xs 和 y) 编码。</span><span class="sxs-lookup"><span data-stu-id="81566-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="81566-108">如果 $x > y $，则会翻转结果 qubit，否则结果 qubit 将保留其状态。</span><span class="sxs-lookup"><span data-stu-id="81566-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="81566-109">输入</span><span class="sxs-lookup"><span data-stu-id="81566-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="81566-110">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81566-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81566-111">LittleEndian qubit register $x $ 的第一个整数编码。</span><span class="sxs-lookup"><span data-stu-id="81566-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="81566-112">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81566-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81566-113">LittleEndian qubit register $y $ 的第二个整数编码。</span><span class="sxs-lookup"><span data-stu-id="81566-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="81566-114">result： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="81566-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="81566-115">如果 $x > y $，将翻转的单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="81566-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81566-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81566-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="81566-117">注解</span><span class="sxs-lookup"><span data-stu-id="81566-117">Remarks</span></span>

<span data-ttu-id="81566-118">使用 $x-y = (x ' + y) "$，其中，表示一个的补码。</span><span class="sxs-lookup"><span data-stu-id="81566-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="81566-119">参考</span><span class="sxs-lookup"><span data-stu-id="81566-119">References</span></span>

- <span data-ttu-id="81566-120">Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton： "A 新的量程波纹-携带加法线路"，2004。</span><span class="sxs-lookup"><span data-stu-id="81566-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="81566-121">Thomas Haener，圣马丁 Roetteler，Krysta Svore： "使用 2n + 2 qubits 和基于 Toffoli 的模块乘法进行因式分解"，2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="81566-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>