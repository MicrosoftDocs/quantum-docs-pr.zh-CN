---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701064"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="764a5-102">DecompositionState 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="764a5-102">DecompositionState user defined type</span></span>

<span data-ttu-id="764a5-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="764a5-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="764a5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="764a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="764a5-105">基于变量索引的分解过程中的状态</span><span class="sxs-lookup"><span data-stu-id="764a5-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="764a5-106">命名项</span><span class="sxs-lookup"><span data-stu-id="764a5-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="764a5-107">永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="764a5-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="764a5-108">Lfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="764a5-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="764a5-109">Rfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="764a5-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="764a5-110">说明</span><span class="sxs-lookup"><span data-stu-id="764a5-110">Description</span></span>

<span data-ttu-id="764a5-111">状态包含当前排列和当前为控制的入口的当前生成的函数，右侧有控制的入口。</span><span class="sxs-lookup"><span data-stu-id="764a5-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>