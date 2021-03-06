---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842060"
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