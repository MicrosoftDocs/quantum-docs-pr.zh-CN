---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696604"
---
# <a name="multiplyi-operation"></a>MultiplyI 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


将整数 `xs` 与整数相乘 `ys` 并将结果存储在中 `result` ，后者最初必须为零。

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ 被乘数 (LittleEndian) 


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ (LittleEndian) 


### <a name="result--littleendian"></a>result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$ 2n $-bit result (LittleEndian) ，其最初必须处于 $ \ket {0} $ 状态。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

使用标准的移位和添加方法来实现乘法。
通过将 $x _i $ 复制到 qubits 控制上的 ancilla qubit，然后控制 ancilla qubit 上的加法，来改进受控版本。