---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203937"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="7e3b1-102">_ComputeJordanWignerBitString 函数</span><span class="sxs-lookup"><span data-stu-id="7e3b1-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="7e3b1-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7e3b1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7e3b1-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7e3b1-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7e3b1-105">用偶数个创建/annihilation 运算符在 fermionic 运算符中的 fermion 索引之间计算 Wigner 字符串的 Z 分量。</span><span class="sxs-lookup"><span data-stu-id="7e3b1-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="7e3b1-106">输入</span><span class="sxs-lookup"><span data-stu-id="7e3b1-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="7e3b1-107">nFermions： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e3b1-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e3b1-108">系统中 fermions 的数目。</span><span class="sxs-lookup"><span data-stu-id="7e3b1-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="7e3b1-109">idxFermions： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7e3b1-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7e3b1-110">fermionic 运算符索引。</span><span class="sxs-lookup"><span data-stu-id="7e3b1-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7e3b1-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="7e3b1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="7e3b1-112">`Bool[]` `true` `PauliZ` 应应用的 Bitstring。</span><span class="sxs-lookup"><span data-stu-id="7e3b1-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>