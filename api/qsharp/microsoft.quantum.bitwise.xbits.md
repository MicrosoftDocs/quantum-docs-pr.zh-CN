---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696404"
---
# <a name="xbits-function"></a>XBits 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

软件包 [](https://nuget.org/packages/)


返回一个整数，该整数表示 Pauli 运算符数组的 X 位。

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>输入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

要以整数形式表示的 Pauli 运算符的数组。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

二进制表示形式为 $ (的整数 $x p_ {62} \, p_ {61} \, \dots .. \, p_0) $，其中 $p _i = $0 如果 `paulis[i]` 为 or，其中 $p _i = `PauliI` `PauliZ` $1 （如果 `paulis[i]` 为或） `PauliX` `PauliY` 。

## <a name="remarks"></a>注解

如果数组的长度大于63，则函数将引发 `paulis` 。

## <a name="see-also"></a>另请参阅

- [ZBits。](xref:Microsoft.Quantum.Bitwise.ZBits)