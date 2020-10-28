---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: RippleCarryAdderD 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: c4466feebb8ff6afcdcb5bf385ec10e807c00537
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696575"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="0d20d-102">RippleCarryAdderD 操作</span><span class="sxs-lookup"><span data-stu-id="0d20d-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="0d20d-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0d20d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0d20d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d20d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d20d-105">可逆的就地波纹-包含两个整数。</span><span class="sxs-lookup"><span data-stu-id="0d20d-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="0d20d-106">假设在 LittleEndian 中编码的两个 $n $ 位整数 `xs` 和 `ys` 一个 qubit，则该操作将计算两个整数的总和，其中包含结果的 $n $ 最低有效位 `ys` ，而执行位被 xored 到 qubit `carry` 。</span><span class="sxs-lookup"><span data-stu-id="0d20d-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0d20d-107">输入</span><span class="sxs-lookup"><span data-stu-id="0d20d-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0d20d-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0d20d-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0d20d-109">LittleEndian qubit register 第一个整数被加数编码。</span><span class="sxs-lookup"><span data-stu-id="0d20d-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0d20d-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0d20d-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0d20d-111">LittleEndian qubit register 编码为第二个整数被加数，将进行修改以容纳总和的 $n $ 最高有效位。</span><span class="sxs-lookup"><span data-stu-id="0d20d-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="0d20d-112">携带： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0d20d-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0d20d-113">携带 qubit，是 xored，其最高有效位是 sum。</span><span class="sxs-lookup"><span data-stu-id="0d20d-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d20d-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d20d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0d20d-115">注解</span><span class="sxs-lookup"><span data-stu-id="0d20d-115">Remarks</span></span>

<span data-ttu-id="0d20d-116">指定的受控操作利用操作的对称和相互取消来改善将控件添加到每个操作的默认实现。</span><span class="sxs-lookup"><span data-stu-id="0d20d-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="0d20d-117">参考</span><span class="sxs-lookup"><span data-stu-id="0d20d-117">References</span></span>

- <span data-ttu-id="0d20d-118">Thomas Draper： "在量程计算机上添加"，2000。</span><span class="sxs-lookup"><span data-stu-id="0d20d-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033