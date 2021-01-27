---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842745"
---
# <a name="modulusl-function"></a><span data-ttu-id="b9c89-102">ModulusL 函数</span><span class="sxs-lookup"><span data-stu-id="b9c89-102">ModulusL function</span></span>

<span data-ttu-id="b9c89-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b9c89-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b9c89-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9c89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9c89-105">计算模的规范 residue `value` `modulus` 。</span><span class="sxs-lookup"><span data-stu-id="b9c89-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="b9c89-106">输入</span><span class="sxs-lookup"><span data-stu-id="b9c89-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="b9c89-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b9c89-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b9c89-108">计算 residue 的值</span><span class="sxs-lookup"><span data-stu-id="b9c89-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="b9c89-109">模数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b9c89-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b9c89-110">Residues 所采用的模数必须为正数</span><span class="sxs-lookup"><span data-stu-id="b9c89-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b9c89-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b9c89-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b9c89-112">0之间的整数 $r $， `modulus - 1` 这可 `value - r` 被模数整除</span><span class="sxs-lookup"><span data-stu-id="b9c89-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="b9c89-113">备注</span><span class="sxs-lookup"><span data-stu-id="b9c89-113">Remarks</span></span>

<span data-ttu-id="b9c89-114">此函数的行为与运算符 `%` 在 c # 和 Q # 中的行为方式有所不同，因为结果中始终是0到之间的一个非负整数 `modulus - 1` ，即使值为负。</span><span class="sxs-lookup"><span data-stu-id="b9c89-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>