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
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Optimization)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示优化单变量函数的结果。

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>命名项

### <a name="coordinate--double"></a>坐标： [Double](xref:microsoft.quantum.lang-ref.double)

找到最佳的输入。
### <a name="value--double"></a>值： [Double](xref:microsoft.quantum.lang-ref.double)

函数返回的值的最佳值。