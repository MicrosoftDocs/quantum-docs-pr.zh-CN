---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203223"
---
# <a name="decomposedon-function"></a>DecomposedOn 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对变量分解

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>描述

给定排列 $ \pi $ (`perm`) ，$i $ () 的索引 `index` ，此方法返回三个排列 $ ( # A5 \ pi_l，\ pi_r) ，\pi ' ) $，以使 $ \ pi_l $ 和 $ \ pi_r $ 的图像不会在其元素中的索引（而不是 $ \pi ' $ 的）中更改其元素中的位。

## <a name="input"></a>输入

### <a name="perm--int"></a>永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)[]，[int](xref:microsoft.quantum.lang-ref.int)[] ) ，[int](xref:microsoft.quantum.lang-ref.int)[] ) 

