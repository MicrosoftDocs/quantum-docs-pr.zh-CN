---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695611"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="bf671-102">AllEqualityFactI 函数</span><span class="sxs-lookup"><span data-stu-id="bf671-102">AllEqualityFactI function</span></span>

<span data-ttu-id="bf671-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bf671-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bf671-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf671-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf671-105">断言整数值的两个数组相等。</span><span class="sxs-lookup"><span data-stu-id="bf671-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bf671-106">输入</span><span class="sxs-lookup"><span data-stu-id="bf671-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="bf671-107">实际： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bf671-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bf671-108">由相关测试用例生成的数组。</span><span class="sxs-lookup"><span data-stu-id="bf671-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="bf671-109">应为： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bf671-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bf671-110">需要从相关测试用例进行计算的数组。</span><span class="sxs-lookup"><span data-stu-id="bf671-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="bf671-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bf671-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bf671-112">如果数组不相等，则为要打印的消息。</span><span class="sxs-lookup"><span data-stu-id="bf671-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf671-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf671-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

