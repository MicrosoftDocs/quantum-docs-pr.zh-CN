---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843119"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="1fc95-102">MeasureInteger 操作</span><span class="sxs-lookup"><span data-stu-id="1fc95-102">MeasureInteger operation</span></span>

<span data-ttu-id="1fc95-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1fc95-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1fc95-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1fc95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1fc95-105">测量量程寄存器的内容并将其转换为整数。</span><span class="sxs-lookup"><span data-stu-id="1fc95-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="1fc95-106">根据标准计算基准（即，的 eigenbasis）执行测量 `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="1fc95-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="1fc95-107">输入</span><span class="sxs-lookup"><span data-stu-id="1fc95-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="1fc95-108">目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1fc95-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1fc95-109">用小字节序编码的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="1fc95-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="1fc95-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fc95-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fc95-111">一个无符号整数，其中包含的度量值 `target` 。</span><span class="sxs-lookup"><span data-stu-id="1fc95-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fc95-112">备注</span><span class="sxs-lookup"><span data-stu-id="1fc95-112">Remarks</span></span>

<span data-ttu-id="1fc95-113">此操作将其输入注册重置为 $ \ket{00\cdots 0} $ 状态，适用于释放回目标计算机。</span><span class="sxs-lookup"><span data-stu-id="1fc95-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fc95-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fc95-114">See Also</span></span>

- [<span data-ttu-id="1fc95-115">Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="1fc95-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)