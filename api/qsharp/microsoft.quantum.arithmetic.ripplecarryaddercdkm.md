---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: RippleCarryAdderCDKM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: 6dcb5193c5d1d059682a79e63e6562aabff7539d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696579"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="a4d06-102">RippleCarryAdderCDKM 操作</span><span class="sxs-lookup"><span data-stu-id="a4d06-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="a4d06-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a4d06-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a4d06-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4d06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4d06-105">可逆的就地波纹-包含两个整数。</span><span class="sxs-lookup"><span data-stu-id="a4d06-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="a4d06-106">说明</span><span class="sxs-lookup"><span data-stu-id="a4d06-106">Description</span></span>

<span data-ttu-id="a4d06-107">假设在 LittleEndian 中编码的两个 $n $ 位整数 `xs` 和 `ys` 一个 qubit，则该操作将计算两个整数的总和，其中包含结果的 $n $ 最低有效位 `ys` ，而执行位被 xored 到 qubit `carry` 。</span><span class="sxs-lookup"><span data-stu-id="a4d06-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="a4d06-108">输入</span><span class="sxs-lookup"><span data-stu-id="a4d06-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a4d06-109">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a4d06-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a4d06-110">LittleEndian qubit register 第一个整数被加数编码。</span><span class="sxs-lookup"><span data-stu-id="a4d06-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a4d06-111">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a4d06-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a4d06-112">LittleEndian qubit register 编码为第二个整数被加数，将修改为持有 sum 的最小有效位。</span><span class="sxs-lookup"><span data-stu-id="a4d06-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="a4d06-113">携带： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4d06-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4d06-114">携带 qubit，是 xored，其最高有效位是 sum。</span><span class="sxs-lookup"><span data-stu-id="a4d06-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4d06-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4d06-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a4d06-116">注解</span><span class="sxs-lookup"><span data-stu-id="a4d06-116">Remarks</span></span>

<span data-ttu-id="a4d06-117">此操作具有与 RippleCarryAdderD 相同的功能，但仅使用一个辅助 qubit，而不是 $n $。</span><span class="sxs-lookup"><span data-stu-id="a4d06-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="a4d06-118">参考</span><span class="sxs-lookup"><span data-stu-id="a4d06-118">References</span></span>

- <span data-ttu-id="a4d06-119">Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton： "A 新的量程波纹-携带加法线路"，2004。</span><span class="sxs-lookup"><span data-stu-id="a4d06-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1