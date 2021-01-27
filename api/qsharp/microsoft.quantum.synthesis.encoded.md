---
uid: Microsoft.Quantum.Synthesis.Encoded
title: 编码函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855486"
---
# <a name="encoded-function"></a><span data-ttu-id="0a687-102">编码函数</span><span class="sxs-lookup"><span data-stu-id="0a687-102">Encoded function</span></span>

<span data-ttu-id="0a687-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0a687-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0a687-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a687-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a687-105">{1,-1}编码事实数据表</span><span class="sxs-lookup"><span data-stu-id="0a687-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0a687-106">输入</span><span class="sxs-lookup"><span data-stu-id="0a687-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="0a687-107">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0a687-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="0a687-108">事实数据表作为真值数组</span><span class="sxs-lookup"><span data-stu-id="0a687-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="0a687-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0a687-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0a687-110">作为整数数组的事实数据表 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="0a687-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="0a687-111">示例</span><span class="sxs-lookup"><span data-stu-id="0a687-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```