---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203087"
---
# <a name="fasthadamardtransformed-function"></a>FastHadamardTransformed 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1}使用 fisher-yates 的方法计算使用编码的布尔函数的 Hadamard 转换

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>输入

### <a name="func--int"></a>func： [Int](xref:microsoft.quantum.lang-ref.int)[]

编码的事实数据表 {-1,1}



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

函数的 Spectral 系数