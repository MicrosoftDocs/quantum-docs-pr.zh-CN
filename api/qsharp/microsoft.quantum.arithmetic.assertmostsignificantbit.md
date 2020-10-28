---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699953"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="17270-102">AssertMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="17270-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="17270-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="17270-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="17270-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17270-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17270-105">断言表示无符号整数的 qubit 寄存器的最重要 qubit 处于特定状态。</span><span class="sxs-lookup"><span data-stu-id="17270-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="17270-106">输入</span><span class="sxs-lookup"><span data-stu-id="17270-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="17270-107">值： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="17270-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="17270-108">要断言的最高位的值。</span><span class="sxs-lookup"><span data-stu-id="17270-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="17270-109">number： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="17270-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="17270-110">检查高位的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="17270-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17270-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17270-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="17270-112">注解</span><span class="sxs-lookup"><span data-stu-id="17270-112">Remarks</span></span>

<span data-ttu-id="17270-113">此操作的受控版本将忽略控件。</span><span class="sxs-lookup"><span data-stu-id="17270-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="17270-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17270-114">See Also</span></span>

- [<span data-ttu-id="17270-115">Microsoft 量子. 断言</span><span class="sxs-lookup"><span data-stu-id="17270-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)