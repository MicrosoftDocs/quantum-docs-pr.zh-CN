---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227771"
---
# <a name="modulusi-function"></a><span data-ttu-id="2401f-102">ModulusI 函数</span><span class="sxs-lookup"><span data-stu-id="2401f-102">ModulusI function</span></span>

<span data-ttu-id="2401f-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2401f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2401f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2401f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2401f-105">计算模的规范 residue `value` `modulus` 。</span><span class="sxs-lookup"><span data-stu-id="2401f-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="2401f-106">输入</span><span class="sxs-lookup"><span data-stu-id="2401f-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="2401f-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2401f-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2401f-108">计算 residue 的值</span><span class="sxs-lookup"><span data-stu-id="2401f-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="2401f-109">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2401f-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2401f-110">Residues 所采用的模数必须为正数</span><span class="sxs-lookup"><span data-stu-id="2401f-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="2401f-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2401f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2401f-112">0之间的整数 $r $， `modulus - 1` 这可 `value - r` 被模数整除</span><span class="sxs-lookup"><span data-stu-id="2401f-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="2401f-113">备注</span><span class="sxs-lookup"><span data-stu-id="2401f-113">Remarks</span></span>

<span data-ttu-id="2401f-114">此函数的行为方式与运算符 `%` 在 c # 和 Q # 中的行为方式相同，因为结果中始终是一个介于0到之间的正整数 `modulus - 1` ，即使值为负。</span><span class="sxs-lookup"><span data-stu-id="2401f-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>