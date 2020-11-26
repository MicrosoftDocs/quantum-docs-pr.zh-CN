---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: d4bae0cba5ee45e8d48070e36efab0159ade9137
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222365"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


反映给定的传统整数的量程寄存器。

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

给定一个量程寄存器，最初处于状态 $ \ sum_i \ alpha_i \ket{i} $，其中每个 $ \ket{i} $ 是表示整数 $i $ 的基本状态，它反映了给定整数 $ \ket{j} $，$ $ \ sum_i ( 的基本状态的寄存器状态，) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $

## <a name="input"></a>输入

### <a name="index--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)

对要反射的基础状态的传统整数进行索引。


### <a name="reg--littleendian"></a>reg： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

此操作就地实现，无需显式分配额外的辅助 qubits。