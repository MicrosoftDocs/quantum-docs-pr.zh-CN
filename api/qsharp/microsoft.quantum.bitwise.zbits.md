---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696399"
---
# <a name="zbits-function"></a><span data-ttu-id="654bf-102">ZBits 函数</span><span class="sxs-lookup"><span data-stu-id="654bf-102">ZBits function</span></span>

<span data-ttu-id="654bf-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="654bf-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="654bf-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="654bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="654bf-105">返回一个整数，该整数表示 Pauli 运算符数组的 Z 位。</span><span class="sxs-lookup"><span data-stu-id="654bf-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="654bf-106">输入</span><span class="sxs-lookup"><span data-stu-id="654bf-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="654bf-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="654bf-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="654bf-108">要以整数形式表示的 Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="654bf-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="654bf-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="654bf-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="654bf-110">二进制表示形式为 $ (的整数 $x p_ {62} \, p_ {61} \, \dots .. \, p_0) $，其中 $p _i = $0 如果 `paulis[i]` 为 or，其中 $p _i = `PauliI` `PauliX` $1 （如果 `paulis[i]` 为或） `PauliY` `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="654bf-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="654bf-111">注解</span><span class="sxs-lookup"><span data-stu-id="654bf-111">Remarks</span></span>

<span data-ttu-id="654bf-112">如果数组的长度大于63，则函数将引发 `paulis` 。</span><span class="sxs-lookup"><span data-stu-id="654bf-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="654bf-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="654bf-113">See Also</span></span>

- [<span data-ttu-id="654bf-114">XBits。</span><span class="sxs-lookup"><span data-stu-id="654bf-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)