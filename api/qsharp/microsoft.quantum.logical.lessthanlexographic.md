---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 3b3ac3f9f8b70307099de60899c969abb2acad7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197664"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="04b22-102">LessThanLexographic 函数</span><span class="sxs-lookup"><span data-stu-id="04b22-102">LessThanLexographic function</span></span>

<span data-ttu-id="04b22-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="04b22-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="04b22-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04b22-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04b22-105">用于实现 `LexographicComparison` 。</span><span class="sxs-lookup"><span data-stu-id="04b22-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="04b22-106">输入</span><span class="sxs-lookup"><span data-stu-id="04b22-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="04b22-107">比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="04b22-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="04b22-108">left： t []</span><span class="sxs-lookup"><span data-stu-id="04b22-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="04b22-109">right： t []</span><span class="sxs-lookup"><span data-stu-id="04b22-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="04b22-110">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="04b22-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="04b22-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="04b22-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="04b22-112">找</span><span class="sxs-lookup"><span data-stu-id="04b22-112">'T</span></span>

