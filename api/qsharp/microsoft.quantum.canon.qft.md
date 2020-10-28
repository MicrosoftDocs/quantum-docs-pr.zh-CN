---
uid: Microsoft.Quantum.Canon.QFT
title: QFT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695980"
---
# <a name="qft-operation"></a><span data-ttu-id="55514-102">QFT 操作</span><span class="sxs-lookup"><span data-stu-id="55514-102">QFT operation</span></span>

<span data-ttu-id="55514-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="55514-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="55514-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55514-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55514-105">对包含大字节序表示形式整数的量程寄存器执行量程傅立叶转换。</span><span class="sxs-lookup"><span data-stu-id="55514-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="55514-106">输入</span><span class="sxs-lookup"><span data-stu-id="55514-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="55514-107">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="55514-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="55514-108">量程傅立叶转换应用于的量程寄存器</span><span class="sxs-lookup"><span data-stu-id="55514-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="55514-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55514-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="55514-110">注解</span><span class="sxs-lookup"><span data-stu-id="55514-110">Remarks</span></span>

<span data-ttu-id="55514-111">输入和输出假定为大字节序编码。</span><span class="sxs-lookup"><span data-stu-id="55514-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="55514-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55514-112">See Also</span></span>

- [<span data-ttu-id="55514-113">Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="55514-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)