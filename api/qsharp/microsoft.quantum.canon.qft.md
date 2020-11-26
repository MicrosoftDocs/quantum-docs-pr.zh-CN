---
uid: Microsoft.Quantum.Canon.QFT
title: QFT 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 8f1aa8c3680a068e500503ca25afa9a49e4ef5bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205519"
---
# <a name="qft-operation"></a><span data-ttu-id="30692-102">QFT 操作</span><span class="sxs-lookup"><span data-stu-id="30692-102">QFT operation</span></span>

<span data-ttu-id="30692-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="30692-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="30692-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30692-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30692-105">对包含大字节序表示形式整数的量程寄存器执行量程傅立叶转换。</span><span class="sxs-lookup"><span data-stu-id="30692-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="30692-106">输入</span><span class="sxs-lookup"><span data-stu-id="30692-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="30692-107">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="30692-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="30692-108">量程傅立叶转换应用于的量程寄存器</span><span class="sxs-lookup"><span data-stu-id="30692-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="30692-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="30692-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="30692-110">备注</span><span class="sxs-lookup"><span data-stu-id="30692-110">Remarks</span></span>

<span data-ttu-id="30692-111">输入和输出假定为大字节序编码。</span><span class="sxs-lookup"><span data-stu-id="30692-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="30692-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30692-112">See Also</span></span>

- [<span data-ttu-id="30692-113">Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="30692-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)