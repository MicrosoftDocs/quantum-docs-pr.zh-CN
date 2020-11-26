---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: 3ded981dc53236a48f1fb8f6ae12e39c17469447
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219441"
---
# <a name="zbits-function"></a>ZBits 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回一个整数，该整数表示 Pauli 运算符数组的 Z 位。

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>输入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

要以整数形式表示的 Pauli 运算符的数组。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

二进制表示形式为 $ (的整数 $x p_ {62} \, p_ {61} \, \dots .. \, p_0) $，其中 $p _i = $0 如果 `paulis[i]` 为 or，其中 $p _i = `PauliI` `PauliX` $1 （如果 `paulis[i]` 为或） `PauliY` `PauliZ` 。

## <a name="remarks"></a>备注

如果数组的长度大于63，则函数将引发 `paulis` 。

## <a name="see-also"></a>另请参阅

- [XBits。](xref:Microsoft.Quantum.Bitwise.XBits)