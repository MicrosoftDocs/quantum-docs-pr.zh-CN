---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847262"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="c8c13-102">BlockEncodingToReflection 函数</span><span class="sxs-lookup"><span data-stu-id="c8c13-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="c8c13-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c8c13-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c8c13-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8c13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8c13-105">将转换为 `BlockEncoding` 等效的 `BLockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="c8c13-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="c8c13-106">也就是说，假设有一个 `BlockEncoding` 用于对某个运算符进行编码的单一 $U $ $H $ 相关，则将其转换为对 `BlockEncodingReflection` 同一运算符进行编码的 $U $，同时满足 $U "^ \Dagger = U" $。</span><span class="sxs-lookup"><span data-stu-id="c8c13-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="c8c13-107">这会将 $U $ 的辅助寄存器大小增加了一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="c8c13-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="c8c13-108">输入</span><span class="sxs-lookup"><span data-stu-id="c8c13-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="c8c13-109">blockEncoding： [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="c8c13-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="c8c13-110">`BlockEncoding`要转换为反射的单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="c8c13-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="c8c13-111">输出： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="c8c13-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="c8c13-112">单一 $U ' $ 共同操作寄存器并对 `a` 其 `s` 进行块编码 $H $，并满足 $U ^ \Dagger = U ' $。</span><span class="sxs-lookup"><span data-stu-id="c8c13-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8c13-113">备注</span><span class="sxs-lookup"><span data-stu-id="c8c13-113">Remarks</span></span>

<span data-ttu-id="c8c13-114">这会将 $U $ 的辅助寄存器大小增加了一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="c8c13-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="c8c13-115">参考</span><span class="sxs-lookup"><span data-stu-id="c8c13-115">References</span></span>

- <span data-ttu-id="c8c13-116">Hamiltonian 模拟 by Qubitization Guang 脱离 Hao Low、Isaac 语 https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="c8c13-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="c8c13-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c13-117">See Also</span></span>

- [<span data-ttu-id="c8c13-118">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="c8c13-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="c8c13-119">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="c8c13-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)