---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696286"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="8e4e6-102">ApplyQuantumFourierTransform 操作</span><span class="sxs-lookup"><span data-stu-id="8e4e6-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="8e4e6-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8e4e6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8e4e6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8e4e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8e4e6-105">对包含小 endian 表示形式整数的量程寄存器执行量程傅立叶转换。</span><span class="sxs-lookup"><span data-stu-id="8e4e6-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="8e4e6-106">输入</span><span class="sxs-lookup"><span data-stu-id="8e4e6-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="8e4e6-107">qs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8e4e6-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8e4e6-108">量程傅立叶转换应用于的量程寄存器</span><span class="sxs-lookup"><span data-stu-id="8e4e6-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e4e6-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e4e6-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8e4e6-110">注解</span><span class="sxs-lookup"><span data-stu-id="8e4e6-110">Remarks</span></span>

<span data-ttu-id="8e4e6-111">输入和输出假定为 little endian 编码。</span><span class="sxs-lookup"><span data-stu-id="8e4e6-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e4e6-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e4e6-112">See Also</span></span>

- [<span data-ttu-id="8e4e6-113">Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="8e4e6-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)