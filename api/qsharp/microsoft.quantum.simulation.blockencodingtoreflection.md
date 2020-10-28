---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700165"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="cb7dd-102">BlockEncodingToReflection 函数</span><span class="sxs-lookup"><span data-stu-id="cb7dd-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="cb7dd-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cb7dd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cb7dd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb7dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb7dd-105">将转换为 `BlockEncoding` 等效的 `BLockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="cb7dd-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="cb7dd-106">也就是说，假设有一个 `BlockEncoding` 用于对某个运算符进行编码的单一 $U $ $H $ 相关，则将其转换为对 `BlockEncodingReflection` 同一运算符进行编码的 $U $，同时满足 $U "^ \Dagger = U" $。</span><span class="sxs-lookup"><span data-stu-id="cb7dd-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="cb7dd-107">这会将 $U $ 的辅助寄存器大小增加了一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="cb7dd-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="cb7dd-108">输入</span><span class="sxs-lookup"><span data-stu-id="cb7dd-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="cb7dd-109">blockEncoding： [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="cb7dd-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="cb7dd-110">`BlockEncoding`要转换为反射的单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="cb7dd-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="cb7dd-111">输出： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="cb7dd-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="cb7dd-112">单一 $U ' $ 共同操作寄存器并对 `a` 其 `s` 进行块编码 $H $，并满足 $U ^ \Dagger = U ' $。</span><span class="sxs-lookup"><span data-stu-id="cb7dd-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb7dd-113">注解</span><span class="sxs-lookup"><span data-stu-id="cb7dd-113">Remarks</span></span>

<span data-ttu-id="cb7dd-114">这会将 $U $ 的辅助寄存器大小增加了一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="cb7dd-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="cb7dd-115">参考</span><span class="sxs-lookup"><span data-stu-id="cb7dd-115">References</span></span>

- <span data-ttu-id="cb7dd-116">Hamiltonian 模拟 by Qubitization Guang 脱离 Hao Low、Isaac 语 https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="cb7dd-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="cb7dd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb7dd-117">See Also</span></span>

- [<span data-ttu-id="cb7dd-118">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="cb7dd-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="cb7dd-119">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="cb7dd-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)