---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696285"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="5f6e9-102">ApplyQuantumFourierTransformBE 操作</span><span class="sxs-lookup"><span data-stu-id="5f6e9-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="5f6e9-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5f6e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5f6e9-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5f6e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5f6e9-105">对包含大字节序表示形式整数的量程寄存器执行量程傅立叶转换。</span><span class="sxs-lookup"><span data-stu-id="5f6e9-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="5f6e9-106">输入</span><span class="sxs-lookup"><span data-stu-id="5f6e9-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="5f6e9-107">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="5f6e9-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="5f6e9-108">量程傅立叶转换应用于的量程寄存器</span><span class="sxs-lookup"><span data-stu-id="5f6e9-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="5f6e9-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5f6e9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5f6e9-110">注解</span><span class="sxs-lookup"><span data-stu-id="5f6e9-110">Remarks</span></span>

<span data-ttu-id="5f6e9-111">输入和输出假定为大字节序编码。</span><span class="sxs-lookup"><span data-stu-id="5f6e9-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f6e9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f6e9-112">See Also</span></span>

- [<span data-ttu-id="5f6e9-113">Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="5f6e9-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="5f6e9-114">Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="5f6e9-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)