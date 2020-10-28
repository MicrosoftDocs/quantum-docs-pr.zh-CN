---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699952"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="8655e-102">AssertPhaseLessThan 操作</span><span class="sxs-lookup"><span data-stu-id="8655e-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="8655e-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8655e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8655e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8655e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8655e-105">断言 `number` PhaseLittleEndian 中已编码的小于 `value` 。</span><span class="sxs-lookup"><span data-stu-id="8655e-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="8655e-106">输入</span><span class="sxs-lookup"><span data-stu-id="8655e-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="8655e-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8655e-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8655e-108">`number` 必须小于此。</span><span class="sxs-lookup"><span data-stu-id="8655e-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="8655e-109">number： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8655e-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="8655e-110">与进行比较的无符号整数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="8655e-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8655e-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8655e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8655e-112">注解</span><span class="sxs-lookup"><span data-stu-id="8655e-112">Remarks</span></span>

<span data-ttu-id="8655e-113">此操作的受控版本将忽略控件。</span><span class="sxs-lookup"><span data-stu-id="8655e-113">The controlled version of this operation ignores controls.</span></span>