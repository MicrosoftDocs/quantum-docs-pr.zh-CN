---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843424"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言表示无符号整数的 qubit 寄存器的最重要 qubit 处于特定状态。

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="value--__invalidresult__"></a>值：__无效 <Result>__

要断言的最高位的值。


### <a name="number--littleendian"></a>number： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

检查高位的无符号整数。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

此操作的受控版本将忽略控件。

## <a name="see-also"></a>另请参阅

- [Microsoft 量子. 断言](xref:Microsoft.Quantum.Intrinsic.Assert)