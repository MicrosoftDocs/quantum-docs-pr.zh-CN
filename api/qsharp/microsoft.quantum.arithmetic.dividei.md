---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699900"
---
# <a name="dividei-operation"></a>DivideI 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


两个量程整数相除。

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

`xs` 将保留余数 `xs - floor(xs/ys) * ys` 并 `result` 保留 `floor(xs/ys)` 。

## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

被除数 $n，将替换为余数。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ 位除数


### <a name="result--littleendian"></a>result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ 位结果，必须先处于状态 $ \ket {0} $，并将替换为整数相除的结果。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

使用标准的移位和减法方法来实现除法。
受控版本是专用化的，因此不需要其他控制。