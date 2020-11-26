---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195369"
---
# <a name="inversemodi-function"></a>InverseModI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回 $b $ $a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要反转的数字


### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)

与数字相反的模数



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

整数 $b $，$a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。