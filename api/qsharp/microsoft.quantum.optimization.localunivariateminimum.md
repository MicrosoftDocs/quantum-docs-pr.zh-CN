---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695318"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="c06dd-102">LocalUnivariateMinimum 函数</span><span class="sxs-lookup"><span data-stu-id="c06dd-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="c06dd-103">命名空间 [：](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="c06dd-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="c06dd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c06dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c06dd-105">使用黄金间隔搜索，返回单变量函数在限定间隔内的本地最小值。</span><span class="sxs-lookup"><span data-stu-id="c06dd-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="c06dd-106">输入</span><span class="sxs-lookup"><span data-stu-id="c06dd-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="c06dd-107">fn： [双](xref:microsoft.quantum.lang-ref.double) -> [双精度](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c06dd-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c06dd-108">要最小化的单变量函数。</span><span class="sxs-lookup"><span data-stu-id="c06dd-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="c06dd-109">边界： ([double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double)) </span><span class="sxs-lookup"><span data-stu-id="c06dd-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="c06dd-110">要在其中找到本地最小值的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c06dd-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="c06dd-111">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c06dd-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c06dd-112">函数输入中的准确性是可接受的。</span><span class="sxs-lookup"><span data-stu-id="c06dd-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="c06dd-113">搜索本地 optima 将继续执行，直到该间隔的宽度比此公差更小。</span><span class="sxs-lookup"><span data-stu-id="c06dd-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="c06dd-114">输出： [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="c06dd-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="c06dd-115">给定函数的本地 optima，位于给定边界内。</span><span class="sxs-lookup"><span data-stu-id="c06dd-115">A local optima of the given function, located within the given bounds.</span></span>