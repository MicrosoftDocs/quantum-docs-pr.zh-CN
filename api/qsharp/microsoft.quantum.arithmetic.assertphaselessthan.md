---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843431"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="3ff9c-102">AssertPhaseLessThan 操作</span><span class="sxs-lookup"><span data-stu-id="3ff9c-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="3ff9c-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3ff9c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3ff9c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ff9c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ff9c-105">断言 `number` PhaseLittleEndian 中已编码的小于 `value` 。</span><span class="sxs-lookup"><span data-stu-id="3ff9c-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3ff9c-106">输入</span><span class="sxs-lookup"><span data-stu-id="3ff9c-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="3ff9c-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ff9c-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ff9c-108">`number` 必须小于此。</span><span class="sxs-lookup"><span data-stu-id="3ff9c-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="3ff9c-109">number： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3ff9c-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="3ff9c-110">与进行比较的无符号整数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="3ff9c-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ff9c-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ff9c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3ff9c-112">备注</span><span class="sxs-lookup"><span data-stu-id="3ff9c-112">Remarks</span></span>

<span data-ttu-id="3ff9c-113">此操作的受控版本将忽略控件。</span><span class="sxs-lookup"><span data-stu-id="3ff9c-113">The controlled version of this operation ignores controls.</span></span>