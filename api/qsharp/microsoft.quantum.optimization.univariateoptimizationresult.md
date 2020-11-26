---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194026"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="b59cd-102">UnivariateOptimizationResult 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="b59cd-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="b59cd-103">命名空间 [：](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="b59cd-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="b59cd-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b59cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b59cd-105">表示优化单变量函数的结果。</span><span class="sxs-lookup"><span data-stu-id="b59cd-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="b59cd-106">命名项</span><span class="sxs-lookup"><span data-stu-id="b59cd-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="b59cd-107">坐标： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b59cd-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b59cd-108">找到最佳的输入。</span><span class="sxs-lookup"><span data-stu-id="b59cd-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="b59cd-109">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b59cd-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b59cd-110">函数返回的值的最佳值。</span><span class="sxs-lookup"><span data-stu-id="b59cd-110">Value returned by the function at its optimum.</span></span>