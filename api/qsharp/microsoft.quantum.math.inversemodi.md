---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700613"
---
# <a name="inversemodi-function"></a>InverseModI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


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