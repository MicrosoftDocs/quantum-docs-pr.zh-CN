---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700612"
---
# <a name="inversemodl-function"></a>InverseModL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


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