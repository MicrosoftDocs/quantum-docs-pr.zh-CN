---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: MultiplySI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 4e7f43f88654f10ece4f9c30c5bfde9a779b18ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222433"
---
# <a name="multiplysi-operation"></a>MultiplySI 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)


将带符号整数与有符号整数相乘 `xs` `ys` 并将结果存储在中 `result` ，后者最初必须为零。

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="xs--signedlittleendian"></a>xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n 位被乘数 (SignedLittleEndian) 


### <a name="ys--signedlittleendian"></a>y) ： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n 位乘法器 (SignedLittleEndian) 


### <a name="result--signedlittleendian"></a>result： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

 (SignedLittleEndian) 的2n 位结果必须处于 $ \ket {0} $ 起初状态。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

