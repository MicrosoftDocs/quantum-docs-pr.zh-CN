---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828753"
---
# <a name="equalitywithintolerancefact-function"></a>EqualityWithinToleranceFact 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示某一传统浮点值具有到给定绝对公差的预期值。

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>输入

### <a name="actual--double"></a>实际： [Double](xref:microsoft.quantum.lang-ref.double)

要检查的数字。


### <a name="expected--double"></a>应为： [Double](xref:microsoft.quantum.lang-ref.double)

预期值。


### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

实际值与预期值的绝对容差。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

