---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 0e131204d3eaff7f99aa9ff7c3c1ae93a1bf611b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846341"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="a8df3-102">RippleCarryAdderNoCarryTTK 操作</span><span class="sxs-lookup"><span data-stu-id="a8df3-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="a8df3-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a8df3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a8df3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8df3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8df3-105">可逆的就地波纹，无需执行即可额外添加两个整数。</span><span class="sxs-lookup"><span data-stu-id="a8df3-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a8df3-106">说明</span><span class="sxs-lookup"><span data-stu-id="a8df3-106">Description</span></span>

<span data-ttu-id="a8df3-107">给定两 $n 个在 LittleEndian 注册和中编码的 $ bit 整数， `xs` `ys` 操作将计算两个整数的总和： $ 2 ^ n $，其中 $n $ 是输入和的位大小 `xs` `ys` 。</span><span class="sxs-lookup"><span data-stu-id="a8df3-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="a8df3-108">它不计算执行位。</span><span class="sxs-lookup"><span data-stu-id="a8df3-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="a8df3-109">输入</span><span class="sxs-lookup"><span data-stu-id="a8df3-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a8df3-110">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a8df3-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a8df3-111">LittleEndian qubit register 第一个整数被加数编码。</span><span class="sxs-lookup"><span data-stu-id="a8df3-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a8df3-112">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a8df3-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a8df3-113">LittleEndian qubit register 编码为第二个整数被加数，将进行修改以容纳总和的 $n $ 最高有效位。</span><span class="sxs-lookup"><span data-stu-id="a8df3-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8df3-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8df3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a8df3-115">备注</span><span class="sxs-lookup"><span data-stu-id="a8df3-115">Remarks</span></span>

<span data-ttu-id="a8df3-116">此操作具有与 RippleCarryAdderTTK 相同的功能，但不会返回带有位。</span><span class="sxs-lookup"><span data-stu-id="a8df3-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="a8df3-117">参考</span><span class="sxs-lookup"><span data-stu-id="a8df3-117">References</span></span>

- <span data-ttu-id="a8df3-118">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro： "量程加法线路和无限制扇出"、量程信息和计算、2010。</span><span class="sxs-lookup"><span data-stu-id="a8df3-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530