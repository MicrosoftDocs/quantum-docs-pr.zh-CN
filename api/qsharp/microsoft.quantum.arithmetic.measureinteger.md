---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699816"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="8d52a-102">MeasureInteger 操作</span><span class="sxs-lookup"><span data-stu-id="8d52a-102">MeasureInteger operation</span></span>

<span data-ttu-id="8d52a-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8d52a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8d52a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d52a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d52a-105">测量量程寄存器的内容并将其转换为整数。</span><span class="sxs-lookup"><span data-stu-id="8d52a-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="8d52a-106">根据标准计算基准（即，的 eigenbasis）执行测量 `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="8d52a-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="8d52a-107">输入</span><span class="sxs-lookup"><span data-stu-id="8d52a-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="8d52a-108">目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8d52a-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8d52a-109">用小字节序编码的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="8d52a-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="8d52a-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d52a-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d52a-111">一个无符号整数，其中包含的度量值 `target` 。</span><span class="sxs-lookup"><span data-stu-id="8d52a-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d52a-112">注解</span><span class="sxs-lookup"><span data-stu-id="8d52a-112">Remarks</span></span>

<span data-ttu-id="8d52a-113">此操作将其输入注册重置为 $ \ket{00\cdots 0} $ 状态，适用于释放回目标计算机。</span><span class="sxs-lookup"><span data-stu-id="8d52a-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d52a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d52a-114">See Also</span></span>

- [<span data-ttu-id="8d52a-115">Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="8d52a-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)