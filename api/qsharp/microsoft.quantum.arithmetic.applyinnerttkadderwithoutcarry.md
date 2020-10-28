---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700041"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="d264d-102">ApplyInnerTTKAdderWithoutCarry 操作</span><span class="sxs-lookup"><span data-stu-id="d264d-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="d264d-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d264d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d264d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d264d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d264d-105">为操作 RippleCarryAdderNoCarryTTK 实现内部加法函数。</span><span class="sxs-lookup"><span data-stu-id="d264d-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="d264d-106">这是与外部操作 conjugated 的内部操作，用于构造完整的提供程序。</span><span class="sxs-lookup"><span data-stu-id="d264d-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d264d-107">输入</span><span class="sxs-lookup"><span data-stu-id="d264d-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d264d-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d264d-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d264d-109">LittleEndian qubit register 将第一个整数被加数输入编码为 RippleCarryAdderNoCarryTTK。</span><span class="sxs-lookup"><span data-stu-id="d264d-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d264d-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d264d-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d264d-111">LittleEndian qubit register 被加数输入的第二个整数。</span><span class="sxs-lookup"><span data-stu-id="d264d-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d264d-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d264d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d264d-113">注解</span><span class="sxs-lookup"><span data-stu-id="d264d-113">Remarks</span></span>

<span data-ttu-id="d264d-114">指定的受控操作利用操作的对称和相互取消来改善将控件添加到每个操作的默认实现。</span><span class="sxs-lookup"><span data-stu-id="d264d-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="d264d-115">参考</span><span class="sxs-lookup"><span data-stu-id="d264d-115">References</span></span>

- <span data-ttu-id="d264d-116">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro： "量程加法线路和无限制扇出"、量程信息和计算、2010。</span><span class="sxs-lookup"><span data-stu-id="d264d-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530