---
uid: Microsoft.Quantum.Canon.ApplyOperationRepeatedlyCA
title: ApplyOperationRepeatedlyCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOperationRepeatedlyCA
qsharp.summary: ''
ms.openlocfilehash: 2ff13b6b3f142437c2ca7a40884ecf1a66c6a083
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209173"
---
# <a name="applyoperationrepeatedlyca-operation"></a><span data-ttu-id="84913-102">ApplyOperationRepeatedlyCA 操作</span><span class="sxs-lookup"><span data-stu-id="84913-102">ApplyOperationRepeatedlyCA operation</span></span>

<span data-ttu-id="84913-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84913-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84913-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84913-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyOperationRepeatedlyCA<'T> (op : ('T => Unit is Adj + Ctl), power : Int, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="84913-105">输入</span><span class="sxs-lookup"><span data-stu-id="84913-105">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="84913-106">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="84913-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="power--int"></a><span data-ttu-id="84913-107">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84913-107">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="target--t"></a><span data-ttu-id="84913-108">目标： t</span><span class="sxs-lookup"><span data-stu-id="84913-108">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="84913-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84913-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="84913-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="84913-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84913-111">找</span><span class="sxs-lookup"><span data-stu-id="84913-111">'T</span></span>

