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
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum 函数

命名空间 [：](xref:Microsoft.Quantum.Optimization)

软件包 [](https://nuget.org/packages/)


使用黄金间隔搜索，返回单变量函数在限定间隔内的本地最小值。

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>输入

### <a name="fn--double---double"></a>fn： [双](xref:microsoft.quantum.lang-ref.double) -> [双精度](xref:microsoft.quantum.lang-ref.double)

要最小化的单变量函数。


### <a name="bounds--doubledouble"></a>边界： ([double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double)) 

要在其中找到本地最小值的时间间隔。


### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

函数输入中的准确性是可接受的。
搜索本地 optima 将继续执行，直到该间隔的宽度比此公差更小。



## <a name="output--univariateoptimizationresult"></a>输出： [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

给定函数的本地 optima，位于给定边界内。