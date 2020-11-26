---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223878"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="47276-102">AllEqualityFactI 函数</span><span class="sxs-lookup"><span data-stu-id="47276-102">AllEqualityFactI function</span></span>

<span data-ttu-id="47276-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="47276-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="47276-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47276-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47276-105">断言整数值的两个数组相等。</span><span class="sxs-lookup"><span data-stu-id="47276-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="47276-106">输入</span><span class="sxs-lookup"><span data-stu-id="47276-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="47276-107">实际： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="47276-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="47276-108">由相关测试用例生成的数组。</span><span class="sxs-lookup"><span data-stu-id="47276-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="47276-109">应为： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="47276-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="47276-110">需要从相关测试用例进行计算的数组。</span><span class="sxs-lookup"><span data-stu-id="47276-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="47276-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="47276-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="47276-112">如果数组不相等，则为要打印的消息。</span><span class="sxs-lookup"><span data-stu-id="47276-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47276-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47276-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

