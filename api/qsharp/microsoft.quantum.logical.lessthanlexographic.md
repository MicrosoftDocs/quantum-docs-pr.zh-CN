---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695167"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="aad76-102">LessThanLexographic 函数</span><span class="sxs-lookup"><span data-stu-id="aad76-102">LessThanLexographic function</span></span>

<span data-ttu-id="aad76-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="aad76-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="aad76-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aad76-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aad76-105">用于实现 `LexographicComparison` 。</span><span class="sxs-lookup"><span data-stu-id="aad76-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="aad76-106">输入</span><span class="sxs-lookup"><span data-stu-id="aad76-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="aad76-107">比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aad76-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="aad76-108">left： t []</span><span class="sxs-lookup"><span data-stu-id="aad76-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="aad76-109">right： t []</span><span class="sxs-lookup"><span data-stu-id="aad76-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="aad76-110">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="aad76-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aad76-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="aad76-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aad76-112">找</span><span class="sxs-lookup"><span data-stu-id="aad76-112">'T</span></span>

