---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695978"
---
# <a name="qftle-operation"></a><span data-ttu-id="4ce34-102">QFTLE 操作</span><span class="sxs-lookup"><span data-stu-id="4ce34-102">QFTLE operation</span></span>

<span data-ttu-id="4ce34-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4ce34-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4ce34-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ce34-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ce34-105">对包含小 endian 表示形式整数的量程寄存器执行量程傅立叶转换。</span><span class="sxs-lookup"><span data-stu-id="4ce34-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="4ce34-106">输入</span><span class="sxs-lookup"><span data-stu-id="4ce34-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="4ce34-107">qs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4ce34-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4ce34-108">量程傅立叶转换应用于的量程寄存器</span><span class="sxs-lookup"><span data-stu-id="4ce34-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ce34-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ce34-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4ce34-110">注解</span><span class="sxs-lookup"><span data-stu-id="4ce34-110">Remarks</span></span>

<span data-ttu-id="4ce34-111">输入和输出假定为 little endian 编码。</span><span class="sxs-lookup"><span data-stu-id="4ce34-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ce34-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ce34-112">See Also</span></span>

- [<span data-ttu-id="4ce34-113">Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="4ce34-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)