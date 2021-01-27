---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: f725bdbaa945a4f87e90fc71930c37642113c21a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846693"
---
# <a name="comparegtsi-operation"></a>CompareGTSI 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)


带符号整数比较的包装器： `result = xs > ys` 。

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="xs--signedlittleendian"></a>xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

第一个 $n $ 位数字


### <a name="ys--signedlittleendian"></a>y) ： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

第二 $n $ 位数字


### <a name="result--qubit"></a>result： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

如果 $xs > y) $，将进行翻转



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

