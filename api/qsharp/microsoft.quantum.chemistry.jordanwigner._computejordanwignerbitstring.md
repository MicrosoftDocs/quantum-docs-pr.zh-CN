---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839527"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString 函数

命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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

## <a name="example"></a>示例

let bitString = _ComputeJordanWignerBitString (6，[0，1，2，6] ) ;bitString 为 [false，false，false，true，true，true，false]。