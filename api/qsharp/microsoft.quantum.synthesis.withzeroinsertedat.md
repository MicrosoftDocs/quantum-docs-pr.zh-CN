---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855199"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="57e79-102">WithZeroInsertedAt 函数</span><span class="sxs-lookup"><span data-stu-id="57e79-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="57e79-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="57e79-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="57e79-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57e79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57e79-105">将0位插入到整数中</span><span class="sxs-lookup"><span data-stu-id="57e79-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="57e79-106">说明</span><span class="sxs-lookup"><span data-stu-id="57e79-106">Description</span></span>

<span data-ttu-id="57e79-107">此操作采用一个整数，插入0位 `position` ，并将更新后的值作为整数返回。</span><span class="sxs-lookup"><span data-stu-id="57e79-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="57e79-108">例如，在第2个 (¥10 _ = 1010_ $) 的位置2处插入0将 {10} {2} 返回数字 18 ($18 _ {10} = 10010_ {2} $) 。</span><span class="sxs-lookup"><span data-stu-id="57e79-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="57e79-109">输入</span><span class="sxs-lookup"><span data-stu-id="57e79-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="57e79-110">位置： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57e79-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57e79-111">插入0的位置</span><span class="sxs-lookup"><span data-stu-id="57e79-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="57e79-112">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57e79-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57e79-113">修改的值</span><span class="sxs-lookup"><span data-stu-id="57e79-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="57e79-114">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57e79-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57e79-115">修改的值</span><span class="sxs-lookup"><span data-stu-id="57e79-115">Modified value</span></span>