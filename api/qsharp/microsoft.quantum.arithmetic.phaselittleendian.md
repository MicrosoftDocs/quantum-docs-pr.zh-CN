---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696599"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="13fd6-102">PhaseLittleEndian 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="13fd6-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="13fd6-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="13fd6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="13fd6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13fd6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13fd6-105">QFT 基础中的小字节端无符号整数。</span><span class="sxs-lookup"><span data-stu-id="13fd6-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="13fd6-106">例如，如果 $ \ket{x} $ 为计算基础中的整数 $x $ 的小 endian 编码，则 $ \operatorname{QFTLE} \ket{x} $ 是 QFT 中 $x $ 的编码。</span><span class="sxs-lookup"><span data-stu-id="13fd6-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="13fd6-107">注解</span><span class="sxs-lookup"><span data-stu-id="13fd6-107">Remarks</span></span>

<span data-ttu-id="13fd6-108">`PhaseLittleEndian`与 `PhaseLE` 文档中的缩写相同。</span><span class="sxs-lookup"><span data-stu-id="13fd6-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="13fd6-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13fd6-109">See Also</span></span>

- [<span data-ttu-id="13fd6-110">Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="13fd6-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="13fd6-111">Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="13fd6-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)