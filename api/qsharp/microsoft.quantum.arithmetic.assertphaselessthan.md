---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223742"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="d4d6b-102">AssertPhaseLessThan 操作</span><span class="sxs-lookup"><span data-stu-id="d4d6b-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="d4d6b-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d4d6b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d4d6b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4d6b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4d6b-105">断言 `number` PhaseLittleEndian 中已编码的小于 `value` 。</span><span class="sxs-lookup"><span data-stu-id="d4d6b-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d4d6b-106">输入</span><span class="sxs-lookup"><span data-stu-id="d4d6b-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="d4d6b-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4d6b-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4d6b-108">`number` 必须小于此。</span><span class="sxs-lookup"><span data-stu-id="d4d6b-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="d4d6b-109">number： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4d6b-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="d4d6b-110">与进行比较的无符号整数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="d4d6b-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4d6b-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4d6b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d4d6b-112">备注</span><span class="sxs-lookup"><span data-stu-id="d4d6b-112">Remarks</span></span>

<span data-ttu-id="d4d6b-113">此操作的受控版本将忽略控件。</span><span class="sxs-lookup"><span data-stu-id="d4d6b-113">The controlled version of this operation ignores controls.</span></span>