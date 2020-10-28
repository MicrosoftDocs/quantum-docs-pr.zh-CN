---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695122"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


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