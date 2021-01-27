---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843030"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="a510d-102">MultiplyI 操作</span><span class="sxs-lookup"><span data-stu-id="a510d-102">MultiplyI operation</span></span>

<span data-ttu-id="a510d-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a510d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a510d-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a510d-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a510d-105">将整数 `xs` 与整数相乘 `ys` 并将结果存储在中 `result` ，后者最初必须为零。</span><span class="sxs-lookup"><span data-stu-id="a510d-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a510d-106">输入</span><span class="sxs-lookup"><span data-stu-id="a510d-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a510d-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a510d-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a510d-108">$n $ 被乘数 (LittleEndian) </span><span class="sxs-lookup"><span data-stu-id="a510d-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a510d-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a510d-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a510d-110">$n $ (LittleEndian) </span><span class="sxs-lookup"><span data-stu-id="a510d-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="a510d-111">result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a510d-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a510d-112">$ 2n $-bit result (LittleEndian) ，其最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="a510d-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a510d-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a510d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a510d-114">备注</span><span class="sxs-lookup"><span data-stu-id="a510d-114">Remarks</span></span>

<span data-ttu-id="a510d-115">使用标准的移位和添加方法来实现乘法。</span><span class="sxs-lookup"><span data-stu-id="a510d-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="a510d-116">通过将 $x _i $ 复制到 qubits 控制上的 ancilla qubit，然后控制 ancilla qubit 上的加法，来改进受控版本。</span><span class="sxs-lookup"><span data-stu-id="a510d-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>