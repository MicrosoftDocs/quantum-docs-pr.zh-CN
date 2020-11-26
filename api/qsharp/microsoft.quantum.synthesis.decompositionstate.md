---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: cd2a55013f1232d4158dd6c33143b7cf6c0aafbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203189"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="c2d56-102">DecompositionState 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="c2d56-102">DecompositionState user defined type</span></span>

<span data-ttu-id="c2d56-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c2d56-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c2d56-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2d56-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2d56-105">基于变量索引的分解过程中的状态</span><span class="sxs-lookup"><span data-stu-id="c2d56-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="c2d56-106">命名项</span><span class="sxs-lookup"><span data-stu-id="c2d56-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="c2d56-107">永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c2d56-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="c2d56-108">Lfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c2d56-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="c2d56-109">Rfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c2d56-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="c2d56-110">描述</span><span class="sxs-lookup"><span data-stu-id="c2d56-110">Description</span></span>

<span data-ttu-id="c2d56-111">状态包含当前排列和当前为控制的入口的当前生成的函数，右侧有控制的入口。</span><span class="sxs-lookup"><span data-stu-id="c2d56-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>