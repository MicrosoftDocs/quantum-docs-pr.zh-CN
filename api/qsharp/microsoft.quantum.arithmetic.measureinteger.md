---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699816"
---
# <a name="measureinteger-operation"></a>MeasureInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


测量量程寄存器的内容并将其转换为整数。 根据标准计算基准（即，的 eigenbasis）执行测量 `PauliZ` 。

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>输入

### <a name="target--littleendian"></a>目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

用小字节序编码的量程寄存器。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

一个无符号整数，其中包含的度量值 `target` 。

## <a name="remarks"></a>注解

此操作将其输入注册重置为 $ \ket{00\cdots 0} $ 状态，适用于释放回目标计算机。

## <a name="see-also"></a>另请参阅

- [Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)