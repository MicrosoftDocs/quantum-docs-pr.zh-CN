---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699953"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


断言表示无符号整数的 qubit 寄存器的最重要 qubit 处于特定状态。

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>输入

### <a name="value--__invalidresult__"></a>值： __无效 <Result>__

要断言的最高位的值。


### <a name="number--littleendian"></a>number： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

检查高位的无符号整数。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

此操作的受控版本将忽略控件。

## <a name="see-also"></a>另请参阅

- [Microsoft 量子. 断言](xref:Microsoft.Quantum.Intrinsic.Assert)