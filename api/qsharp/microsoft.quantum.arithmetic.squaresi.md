---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696566"
---
# <a name="squaresi-operation"></a>SquareSI 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


方形有符号整数， `xs` 并将结果存储在中 `result` ，后者最初必须为零。

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a>输入

### <a name="xs--signedlittleendian"></a>xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n 位整数到平方 (SignedLittleEndian) 


### <a name="result--signedlittleendian"></a>result： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

 (SignedLittleEndian) 的2n 位结果必须处于 $ \ket {0} $ 起初状态。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

实现依赖于 IntegerSquare。