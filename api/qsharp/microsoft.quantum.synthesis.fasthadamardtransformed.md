---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855458"
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

## <a name="example"></a>示例

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```