---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223776"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="0a70e-102">AssertMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="0a70e-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="0a70e-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0a70e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0a70e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a70e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a70e-105">断言表示无符号整数的 qubit 寄存器的最重要 qubit 处于特定状态。</span><span class="sxs-lookup"><span data-stu-id="0a70e-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0a70e-106">输入</span><span class="sxs-lookup"><span data-stu-id="0a70e-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="0a70e-107">值：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="0a70e-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="0a70e-108">要断言的最高位的值。</span><span class="sxs-lookup"><span data-stu-id="0a70e-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="0a70e-109">number： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0a70e-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0a70e-110">检查高位的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="0a70e-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a70e-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a70e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0a70e-112">备注</span><span class="sxs-lookup"><span data-stu-id="0a70e-112">Remarks</span></span>

<span data-ttu-id="0a70e-113">此操作的受控版本将忽略控件。</span><span class="sxs-lookup"><span data-stu-id="0a70e-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a70e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a70e-114">See Also</span></span>

- [<span data-ttu-id="0a70e-115">Microsoft 量子. 断言</span><span class="sxs-lookup"><span data-stu-id="0a70e-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)