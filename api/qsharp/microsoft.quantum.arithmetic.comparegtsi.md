---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699920"
---
# <a name="comparegtsi-operation"></a>CompareGTSI 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


带符号整数比较的包装器： `result = xs > ys` 。

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="xs--signedlittleendian"></a>xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

第一个 $n $ 位数字


### <a name="ys--signedlittleendian"></a>y) ： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

第二 $n $ 位数字


### <a name="result--qubit"></a>result： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

如果 $xs > y) $，将进行翻转



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

