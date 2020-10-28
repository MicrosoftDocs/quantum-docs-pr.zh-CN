---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695844"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString 函数

命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

软件包 [](https://nuget.org/packages/)


用偶数个创建/annihilation 运算符在 fermionic 运算符中的 fermion 索引之间计算 Wigner 字符串的 Z 分量。

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>输入

### <a name="nfermions--int"></a>nFermions： [Int](xref:microsoft.quantum.lang-ref.int)

系统中 fermions 的数目。


### <a name="idxfermions--int"></a>idxFermions： [Int](xref:microsoft.quantum.lang-ref.int)[]

fermionic 运算符索引。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` `true` `PauliZ` 应应用的 Bitstring。