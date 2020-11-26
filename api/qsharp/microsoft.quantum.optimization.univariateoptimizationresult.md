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