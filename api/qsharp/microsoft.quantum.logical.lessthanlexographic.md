---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 716f58b747e9f58c338670271bb2e7aed96fe98c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815648"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="dbd40-102">LessThanLexographic 函数</span><span class="sxs-lookup"><span data-stu-id="dbd40-102">LessThanLexographic function</span></span>

<span data-ttu-id="dbd40-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dbd40-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dbd40-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbd40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbd40-105">用于实现 `LexographicComparison` 。</span><span class="sxs-lookup"><span data-stu-id="dbd40-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="dbd40-106">输入</span><span class="sxs-lookup"><span data-stu-id="dbd40-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="dbd40-107">比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dbd40-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="dbd40-108">left： t []</span><span class="sxs-lookup"><span data-stu-id="dbd40-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="dbd40-109">right： t []</span><span class="sxs-lookup"><span data-stu-id="dbd40-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="dbd40-110">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="dbd40-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dbd40-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="dbd40-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dbd40-112">找</span><span class="sxs-lookup"><span data-stu-id="dbd40-112">'T</span></span>

