---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: a7043b9c670f79e270180c583fef56b70c1a3bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830889"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="cc361-102">AllEqualityFactI 函数</span><span class="sxs-lookup"><span data-stu-id="cc361-102">AllEqualityFactI function</span></span>

<span data-ttu-id="cc361-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cc361-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cc361-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc361-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc361-105">断言整数值的两个数组相等。</span><span class="sxs-lookup"><span data-stu-id="cc361-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cc361-106">输入</span><span class="sxs-lookup"><span data-stu-id="cc361-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="cc361-107">实际： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cc361-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cc361-108">由相关测试用例生成的数组。</span><span class="sxs-lookup"><span data-stu-id="cc361-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="cc361-109">应为： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cc361-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cc361-110">需要从相关测试用例进行计算的数组。</span><span class="sxs-lookup"><span data-stu-id="cc361-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="cc361-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cc361-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cc361-112">如果数组不相等，则为要打印的消息。</span><span class="sxs-lookup"><span data-stu-id="cc361-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc361-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc361-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

