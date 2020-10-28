---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696404"
---
# <a name="xbits-function"></a><span data-ttu-id="7e3c3-102">XBits 函数</span><span class="sxs-lookup"><span data-stu-id="7e3c3-102">XBits function</span></span>

<span data-ttu-id="7e3c3-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="7e3c3-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="7e3c3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e3c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e3c3-105">返回一个整数，该整数表示 Pauli 运算符数组的 X 位。</span><span class="sxs-lookup"><span data-stu-id="7e3c3-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="7e3c3-106">输入</span><span class="sxs-lookup"><span data-stu-id="7e3c3-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="7e3c3-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="7e3c3-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="7e3c3-108">要以整数形式表示的 Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="7e3c3-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="7e3c3-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e3c3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e3c3-110">二进制表示形式为 $ (的整数 $x p_ {62} \, p_ {61} \, \dots .. \, p_0) $，其中 $p _i = $0 如果 `paulis[i]` 为 or，其中 $p _i = `PauliI` `PauliZ` $1 （如果 `paulis[i]` 为或） `PauliX` `PauliY` 。</span><span class="sxs-lookup"><span data-stu-id="7e3c3-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e3c3-111">注解</span><span class="sxs-lookup"><span data-stu-id="7e3c3-111">Remarks</span></span>

<span data-ttu-id="7e3c3-112">如果数组的长度大于63，则函数将引发 `paulis` 。</span><span class="sxs-lookup"><span data-stu-id="7e3c3-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e3c3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e3c3-113">See Also</span></span>

- [<span data-ttu-id="7e3c3-114">ZBits。</span><span class="sxs-lookup"><span data-stu-id="7e3c3-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)