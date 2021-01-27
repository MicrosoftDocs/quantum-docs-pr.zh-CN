---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854573"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="5a1cc-102">UnivariateOptimizationResult 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="5a1cc-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="5a1cc-103">命名空间 [：](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="5a1cc-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="5a1cc-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a1cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a1cc-105">表示优化单变量函数的结果。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="5a1cc-106">命名项</span><span class="sxs-lookup"><span data-stu-id="5a1cc-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="5a1cc-107">坐标： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5a1cc-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5a1cc-108">找到最佳的输入。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="5a1cc-109">值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5a1cc-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5a1cc-110">函数返回的值的最佳值。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-110">Value returned by the function at its optimum.</span></span>