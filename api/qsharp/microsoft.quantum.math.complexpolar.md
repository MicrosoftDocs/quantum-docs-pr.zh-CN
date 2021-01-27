---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847347"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示极坐标形式的复数。

复数的极坐标表示形式为 $c = r e ^ {i t} $。

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>命名项

### <a name="magnitude--double"></a>数量级： [Double](xref:microsoft.quantum.lang-ref.double)

$C $ $r \ge $0 的绝对值。
### <a name="argument--double"></a>参数： [Double](xref:microsoft.quantum.lang-ref.double)

$C $ 的 \in \mathbb R $ $t 阶段。