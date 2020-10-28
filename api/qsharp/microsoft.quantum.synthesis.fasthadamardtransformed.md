---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701056"
---
# <a name="fasthadamardtransformed-function"></a>FastHadamardTransformed 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


{-1,1}使用 fisher-yates 的方法计算使用编码的布尔函数的 Hadamard 转换

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>输入

### <a name="func--int"></a>func： [Int](xref:microsoft.quantum.lang-ref.int)[]

编码的事实数据表 {-1,1}



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

函数的 Spectral 系数