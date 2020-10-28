---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700457"
---
# <a name="modulusi-function"></a><span data-ttu-id="f738b-102">ModulusI 函数</span><span class="sxs-lookup"><span data-stu-id="f738b-102">ModulusI function</span></span>

<span data-ttu-id="f738b-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f738b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f738b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f738b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f738b-105">计算模的规范 residue `value` `modulus` 。</span><span class="sxs-lookup"><span data-stu-id="f738b-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f738b-106">输入</span><span class="sxs-lookup"><span data-stu-id="f738b-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="f738b-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f738b-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f738b-108">计算 residue 的值</span><span class="sxs-lookup"><span data-stu-id="f738b-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="f738b-109">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f738b-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f738b-110">Residues 所采用的模数必须为正数</span><span class="sxs-lookup"><span data-stu-id="f738b-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="f738b-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f738b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f738b-112">0之间的整数 $r $， `modulus - 1` 这可 `value - r` 被模数整除</span><span class="sxs-lookup"><span data-stu-id="f738b-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="f738b-113">注解</span><span class="sxs-lookup"><span data-stu-id="f738b-113">Remarks</span></span>

<span data-ttu-id="f738b-114">此函数的行为方式与运算符 `%` 在 c # 和 Q # 中的行为方式相同，因为结果中始终是一个介于0到之间的正整数 `modulus - 1` ，即使值为负。</span><span class="sxs-lookup"><span data-stu-id="f738b-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>