---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846606"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="e3e01-102">IncrementByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="e3e01-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="e3e01-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e3e01-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e3e01-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3e01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3e01-105">按整数常量执行 qubit 寄存器的模块化增量。</span><span class="sxs-lookup"><span data-stu-id="e3e01-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e3e01-106">说明</span><span class="sxs-lookup"><span data-stu-id="e3e01-106">Description</span></span>

<span data-ttu-id="e3e01-107">通过 `increment` `modulus` $y $ $N $ 和在中编码的整数，让我们以 $a $ 表示。 `target`</span><span class="sxs-lookup"><span data-stu-id="e3e01-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="e3e01-108">然后，操作执行以下转换： \begin{align} \ket{y} \mapsto \ket{ (y + a) \operatorname{mod} N} \end{align} 整数以小 endian 格式编码。</span><span class="sxs-lookup"><span data-stu-id="e3e01-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="e3e01-109">输入</span><span class="sxs-lookup"><span data-stu-id="e3e01-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="e3e01-110">增量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3e01-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3e01-111">要添加到 $y $ $a $ 的整数增量。</span><span class="sxs-lookup"><span data-stu-id="e3e01-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e3e01-112">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3e01-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3e01-113">整数 $N $ mods $y + a $。</span><span class="sxs-lookup"><span data-stu-id="e3e01-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="e3e01-114">目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e3e01-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e3e01-115">`LittleEndian`$A $ 添加到的格式中的整数 $y $ `increment` 。</span><span class="sxs-lookup"><span data-stu-id="e3e01-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3e01-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3e01-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e3e01-117">备注</span><span class="sxs-lookup"><span data-stu-id="e3e01-117">Remarks</span></span>

<span data-ttu-id="e3e01-118">假定目标的初始值小于 $N $，并且 $a $ $N 增量小于 $。</span><span class="sxs-lookup"><span data-stu-id="e3e01-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="e3e01-119">请注意， <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> 在基础上实现相同的操作 `PhaseLittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="e3e01-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3e01-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3e01-120">See Also</span></span>

- [<span data-ttu-id="e3e01-121">IncrementPhaseByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="e3e01-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)