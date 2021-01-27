---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835620"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients 函数

命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


展开 Jordan-Wigner 系数的精简表示形式，以便在这些条款和 Pauli 条款之间获取一对一的映射。

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>输入

### <a name="coeff--double"></a>coeff： [Double](xref:microsoft.quantum.lang-ref.double)[]

作为从 Jordan-Wigner Hamiltonian 数据结构读取的系数的数组。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner 术语的类型。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)[]

扩展的系数数组，每个 Pauli 项一个。