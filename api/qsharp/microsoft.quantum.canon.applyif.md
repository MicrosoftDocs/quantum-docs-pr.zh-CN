---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841873"
---
# <a name="applyif-operation"></a><span data-ttu-id="42107-102">ApplyIf 操作</span><span class="sxs-lookup"><span data-stu-id="42107-102">ApplyIf operation</span></span>

<span data-ttu-id="42107-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42107-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42107-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42107-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42107-105">应用可在传统上使用的操作。</span><span class="sxs-lookup"><span data-stu-id="42107-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="42107-106">说明</span><span class="sxs-lookup"><span data-stu-id="42107-106">Description</span></span>

<span data-ttu-id="42107-107">给定一个操作 `op` 和一个位值 `bit` 后， `op` 如果为，则应用于 `target` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="42107-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="42107-108">如果 `false` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="42107-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="42107-109">输入</span><span class="sxs-lookup"><span data-stu-id="42107-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="42107-110">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42107-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="42107-111">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="42107-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="42107-112">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="42107-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="42107-113">用于控制是否应用 op 的布尔值。</span><span class="sxs-lookup"><span data-stu-id="42107-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="42107-114">目标： t</span><span class="sxs-lookup"><span data-stu-id="42107-114">target : 'T</span></span>

<span data-ttu-id="42107-115">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="42107-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42107-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42107-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="42107-117">类型参数</span><span class="sxs-lookup"><span data-stu-id="42107-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42107-118">找</span><span class="sxs-lookup"><span data-stu-id="42107-118">'T</span></span>

<span data-ttu-id="42107-119">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="42107-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="42107-120">示例</span><span class="sxs-lookup"><span data-stu-id="42107-120">Example</span></span>

<span data-ttu-id="42107-121">下面的 qubits 将注册为一个计算基础状态，该状态由给定为值数组的传统位字符串表示 `Bool` ：</span><span class="sxs-lookup"><span data-stu-id="42107-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="42107-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42107-122">See Also</span></span>

- [<span data-ttu-id="42107-123">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="42107-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="42107-124">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="42107-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="42107-125">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="42107-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)