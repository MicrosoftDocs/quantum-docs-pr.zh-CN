---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 79dcf65956ba9436fb6fdd452f22f35d4852d6f8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213695"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="545e7-102">AllEqualityFactB 函数</span><span class="sxs-lookup"><span data-stu-id="545e7-102">AllEqualityFactB function</span></span>

<span data-ttu-id="545e7-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="545e7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="545e7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="545e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="545e7-105">断言布尔值的两个数组相等。</span><span class="sxs-lookup"><span data-stu-id="545e7-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="545e7-106">输入</span><span class="sxs-lookup"><span data-stu-id="545e7-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="545e7-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="545e7-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="545e7-108">由相关测试用例生成的数组。</span><span class="sxs-lookup"><span data-stu-id="545e7-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="545e7-109">应为： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="545e7-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="545e7-110">需要从相关测试用例进行计算的数组。</span><span class="sxs-lookup"><span data-stu-id="545e7-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="545e7-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="545e7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="545e7-112">如果数组不相等，则为要打印的消息。</span><span class="sxs-lookup"><span data-stu-id="545e7-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="545e7-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="545e7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

