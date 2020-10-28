---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: RippleCarryAdderTTK 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 5366ace36e63d361a439bfc5a1a78fdf9a353062
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696571"
---
# <a name="ripplecarryadderttk-operation"></a><span data-ttu-id="fb410-102">RippleCarryAdderTTK 操作</span><span class="sxs-lookup"><span data-stu-id="fb410-102">RippleCarryAdderTTK operation</span></span>

<span data-ttu-id="fb410-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fb410-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fb410-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb410-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb410-105">可逆的就地波纹-包含两个整数。</span><span class="sxs-lookup"><span data-stu-id="fb410-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="fb410-106">假设在 LittleEndian 中编码的两个 $n $ 位整数 `xs` 和 `ys` 一个 qubit，则该操作将计算两个整数的总和，其中包含结果的 $n $ 最低有效位 `ys` ，而执行位被 xored 到 qubit `carry` 。</span><span class="sxs-lookup"><span data-stu-id="fb410-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="fb410-107">输入</span><span class="sxs-lookup"><span data-stu-id="fb410-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="fb410-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fb410-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fb410-109">LittleEndian qubit register 第一个整数被加数编码。</span><span class="sxs-lookup"><span data-stu-id="fb410-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="fb410-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fb410-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fb410-111">LittleEndian qubit register 编码为第二个整数被加数，将进行修改以容纳总和的 $n $ 最高有效位。</span><span class="sxs-lookup"><span data-stu-id="fb410-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="fb410-112">携带： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fb410-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fb410-113">携带 qubit，是 xored，其最高有效位是 sum。</span><span class="sxs-lookup"><span data-stu-id="fb410-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fb410-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb410-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fb410-115">注解</span><span class="sxs-lookup"><span data-stu-id="fb410-115">Remarks</span></span>

<span data-ttu-id="fb410-116">此操作与 RippleCarryAdderD 和 RippleCarryAdderCDKM 具有相同的功能，但不使用任何 ancilla qubits。</span><span class="sxs-lookup"><span data-stu-id="fb410-116">This operation has the same functionality as RippleCarryAdderD and, RippleCarryAdderCDKM but does not use any ancilla qubits.</span></span>

## <a name="references"></a><span data-ttu-id="fb410-117">参考</span><span class="sxs-lookup"><span data-stu-id="fb410-117">References</span></span>

- <span data-ttu-id="fb410-118">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro： "量程加法线路和无限制扇出"、量程信息和计算、2010。</span><span class="sxs-lookup"><span data-stu-id="fb410-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530