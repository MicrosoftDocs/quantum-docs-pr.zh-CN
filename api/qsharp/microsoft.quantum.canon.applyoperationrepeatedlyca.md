---
uid: Microsoft.Quantum.Canon.ApplyOperationRepeatedlyCA
title: ApplyOperationRepeatedlyCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOperationRepeatedlyCA
qsharp.summary: ''
ms.openlocfilehash: 7af80b4f310aa6f7fbb616d8249d2b7c5a0b7edf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841633"
---
# <a name="applyoperationrepeatedlyca-operation"></a><span data-ttu-id="59b59-102">ApplyOperationRepeatedlyCA 操作</span><span class="sxs-lookup"><span data-stu-id="59b59-102">ApplyOperationRepeatedlyCA operation</span></span>

<span data-ttu-id="59b59-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59b59-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59b59-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59b59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyOperationRepeatedlyCA<'T> (op : ('T => Unit is Adj + Ctl), power : Int, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="59b59-105">输入</span><span class="sxs-lookup"><span data-stu-id="59b59-105">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="59b59-106">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="59b59-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="power--int"></a><span data-ttu-id="59b59-107">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59b59-107">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="target--t"></a><span data-ttu-id="59b59-108">目标： t</span><span class="sxs-lookup"><span data-stu-id="59b59-108">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="59b59-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59b59-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="59b59-110">类型参数</span><span class="sxs-lookup"><span data-stu-id="59b59-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59b59-111">找</span><span class="sxs-lookup"><span data-stu-id="59b59-111">'T</span></span>

