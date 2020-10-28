---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701065"
---
# <a name="decomposedon-function"></a>DecomposedOn 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


对变量分解

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>说明

给定排列 $ \pi $ (`perm`) ，$i $ () 的索引 `index` ，此方法返回三个排列 $ ( # A5 \ pi_l，\ pi_r) ，\pi ' ) $，以使 $ \ pi_l $ 和 $ \ pi_r $ 的图像不会在其元素中的索引（而不是 $ \pi ' $ 的）中更改其元素中的位。

## <a name="input"></a>输入

### <a name="perm--int"></a>永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)[]，[int](xref:microsoft.quantum.lang-ref.int)[] ) ，[int](xref:microsoft.quantum.lang-ref.int)[] ) 

