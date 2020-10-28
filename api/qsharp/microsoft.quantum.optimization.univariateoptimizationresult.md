---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700809"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Optimization)

软件包 [](https://nuget.org/packages/)


表示优化单变量函数的结果。

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>命名项

### <a name="coordinate--double"></a>坐标： [Double](xref:microsoft.quantum.lang-ref.double)

找到最佳的输入。
### <a name="value--double"></a>值： [Double](xref:microsoft.quantum.lang-ref.double)

函数返回的值的最佳值。