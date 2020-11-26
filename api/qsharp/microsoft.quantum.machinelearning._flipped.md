---
uid: Microsoft.Quantum.MachineLearning._Flipped
title: _Flipped 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _Flipped
qsharp.summary: ''
ms.openlocfilehash: 7799b03a791466a8ae6c62168812437e8b875fbb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212233"
---
# <a name="_flipped-function"></a><span data-ttu-id="63e6a-102">_Flipped 函数</span><span class="sxs-lookup"><span data-stu-id="63e6a-102">_Flipped function</span></span>

<span data-ttu-id="63e6a-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="63e6a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="63e6a-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="63e6a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>




```qsharp
function _Flipped<'TInput1, 'TInput2, 'TOutput> (fn : (('TInput1, 'TInput2) -> 'TOutput)) : (('TInput2, 'TInput1) -> 'TOutput)
```


## <a name="input"></a><span data-ttu-id="63e6a-105">输入</span><span class="sxs-lookup"><span data-stu-id="63e6a-105">Input</span></span>

### <a name="fn--tinput1tinput2---toutput"></a><span data-ttu-id="63e6a-106">fn： ( "TInput1"，"TInput2) ->" TOutput</span><span class="sxs-lookup"><span data-stu-id="63e6a-106">fn : ('TInput1,'TInput2) -> 'TOutput</span></span>





## <a name="output--tinput2tinput1---toutput"></a><span data-ttu-id="63e6a-107">输出： ( "TInput2，" TInput1) -> "TOutput</span><span class="sxs-lookup"><span data-stu-id="63e6a-107">Output : ('TInput2,'TInput1) -> 'TOutput</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63e6a-108">类型参数</span><span class="sxs-lookup"><span data-stu-id="63e6a-108">Type Parameters</span></span>

### <a name="tinput1"></a><span data-ttu-id="63e6a-109">'TInput1</span><span class="sxs-lookup"><span data-stu-id="63e6a-109">'TInput1</span></span>


### <a name="tinput2"></a><span data-ttu-id="63e6a-110">'TInput2</span><span class="sxs-lookup"><span data-stu-id="63e6a-110">'TInput2</span></span>


### <a name="toutput"></a><span data-ttu-id="63e6a-111">'TOutput</span><span class="sxs-lookup"><span data-stu-id="63e6a-111">'TOutput</span></span>

