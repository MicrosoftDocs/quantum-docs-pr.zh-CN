---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 0d768114c84025a067e0b60762e6834fbd36deb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228179"
---
# <a name="inversemodl-function"></a>InverseModL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回 $b $ $a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>输入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要反转的数字


### <a name="modulus--bigint"></a>模数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

与数字相反的模数



## <a name="output--bigint"></a>输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

整数 $b $，$a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。