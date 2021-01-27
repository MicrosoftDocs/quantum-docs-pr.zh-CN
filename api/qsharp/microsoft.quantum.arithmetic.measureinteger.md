---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843119"
---
# <a name="measureinteger-operation"></a>MeasureInteger 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


测量量程寄存器的内容并将其转换为整数。 根据标准计算基准（即，的 eigenbasis）执行测量 `PauliZ` 。

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>输入

### <a name="target--littleendian"></a>目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

用小字节序编码的量程寄存器。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

一个无符号整数，其中包含的度量值 `target` 。

## <a name="remarks"></a>备注

此操作将其输入注册重置为 $ \ket{00\cdots 0} $ 状态，适用于释放回目标计算机。

## <a name="see-also"></a>另请参阅

- [Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)