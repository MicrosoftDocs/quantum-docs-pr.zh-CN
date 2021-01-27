---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853127"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="4955a-102">FiveQubitCodeRecoveryFn 函数</span><span class="sxs-lookup"><span data-stu-id="4955a-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="4955a-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4955a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4955a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4955a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4955a-105">返回一个函数，该函数通过表查找⟦5，1，3⟧量程代码，将错误症状度量映射到相应的纠错 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="4955a-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="4955a-106">输出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="4955a-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="4955a-107">采用症状度量的类型的函数 `RecoveryFn` `Result[]` ，并返回 `Pauli[]` 更正检测到的错误的运算符。</span><span class="sxs-lookup"><span data-stu-id="4955a-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="4955a-108">备注</span><span class="sxs-lookup"><span data-stu-id="4955a-108">Remarks</span></span>

<span data-ttu-id="4955a-109">通过循环访问权重 $1 $ 的所有错误，我们获取总计 $ 3 \ 乘以 5 = 15 $ 可能的非普通 syndromes。</span><span class="sxs-lookup"><span data-stu-id="4955a-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="4955a-110">除了标识，还生成了一个错误表和相应的症状。</span><span class="sxs-lookup"><span data-stu-id="4955a-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="4955a-111">对于5个 qubit 代码，此表由提供： $X \_ 1： (0，0，0，1) ;X \_ 2： (1，0，0，0) ;X \_ 3： (1，1，0，0) ;X \_ 4： (0，1，1，0) ;X \_ 5： (0，0，1，1) $，$Z \_ 1： (1，0，1，0) ;Z \_ 2： (0，1，0，1) ;Z \_ 3： (0，0，1，0) ;Z \_ 4： (1，0，0，1) ;Z \_ 5： (0、1、0、0) $ $Y 通过添加 $X _i $ 和 $Z _i $ syndromes 获取 _i $。</span><span class="sxs-lookup"><span data-stu-id="4955a-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="4955a-112">请注意，表查找恢复中的排序通过使用 little endian) 将 bitvectors 转换为整数 (提供。</span><span class="sxs-lookup"><span data-stu-id="4955a-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="4955a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4955a-113">See Also</span></span>

- [<span data-ttu-id="4955a-114">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="4955a-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)