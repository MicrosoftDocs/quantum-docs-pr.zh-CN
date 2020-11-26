---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222416"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="e2f82-102">PhaseLittleEndian 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="e2f82-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="e2f82-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e2f82-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e2f82-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2f82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2f82-105">QFT 基础中的小字节端无符号整数。</span><span class="sxs-lookup"><span data-stu-id="e2f82-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="e2f82-106">例如，如果 $ \ket{x} $ 为计算基础中的整数 $x $ 的小 endian 编码，则 $ \operatorname{QFTLE} \ket{x} $ 是 QFT 中 $x $ 的编码。</span><span class="sxs-lookup"><span data-stu-id="e2f82-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="e2f82-107">备注</span><span class="sxs-lookup"><span data-stu-id="e2f82-107">Remarks</span></span>

<span data-ttu-id="e2f82-108">`PhaseLittleEndian`与 `PhaseLE` 文档中的缩写相同。</span><span class="sxs-lookup"><span data-stu-id="e2f82-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2f82-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2f82-109">See Also</span></span>

- [<span data-ttu-id="e2f82-110">Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="e2f82-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="e2f82-111">Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="e2f82-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)