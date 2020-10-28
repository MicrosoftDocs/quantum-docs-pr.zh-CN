---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 5b8afe222d197eb7d342ac45f027f2de9130b61a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695505"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="26828-102">FiveQubitCodeRecoveryFn 函数</span><span class="sxs-lookup"><span data-stu-id="26828-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="26828-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="26828-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="26828-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26828-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26828-105">返回一个函数，该函数通过表查找⟦5，1，3⟧量程代码，将错误症状度量映射到相应的纠错 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="26828-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="26828-106">输出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="26828-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="26828-107">采用症状度量的类型的函数 `RecoveryFn` `Result[]` ，并返回 `Pauli[]` 更正检测到的错误的运算符。</span><span class="sxs-lookup"><span data-stu-id="26828-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="26828-108">注解</span><span class="sxs-lookup"><span data-stu-id="26828-108">Remarks</span></span>

<span data-ttu-id="26828-109">通过循环访问权重 $1 $ 的所有错误，我们获取总计 $ 3 \ 乘以 5 = 15 $ 可能的非普通 syndromes。</span><span class="sxs-lookup"><span data-stu-id="26828-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="26828-110">除了标识，还生成了一个错误表和相应的症状。</span><span class="sxs-lookup"><span data-stu-id="26828-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="26828-111">对于5个 qubit 代码，此表由提供： $X \_ 1： (0，0，0，1) ;X \_ 2： (1，0，0，0) ;X \_ 3： (1，1，0，0) ;X \_ 4： (0，1，1，0) ;X \_ 5： (0，0，1，1) $，$Z \_ 1： (1，0，1，0) ;Z \_ 2： (0，1，0，1) ;Z \_ 3： (0，0，1，0) ;Z \_ 4： (1，0，0，1) ;Z \_ 5： (0、1、0、0) $ $Y 通过添加 $X _i $ 和 $Z _i $ syndromes 获取 _i $。</span><span class="sxs-lookup"><span data-stu-id="26828-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="26828-112">请注意，表查找恢复中的排序通过使用 little endian) 将 bitvectors 转换为整数 (提供。</span><span class="sxs-lookup"><span data-stu-id="26828-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="26828-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26828-113">See Also</span></span>

- [<span data-ttu-id="26828-114">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="26828-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)