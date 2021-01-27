---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834234"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定位字符串后，将返回一个 qubit Pauli 运算符，该运算符表示为一个 qubit Pauli 运算符的数组。

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>输入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

要应用于 qubits 的 Pauli 运算符 `bitsApply == bits[idx]` 。


### <a name="bitapply--bool"></a>bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果 bit 为此值，则应用 Pauli。


### <a name="bits--bool"></a>bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

布尔数组。



## <a name="output--pauli"></a>Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>备注

布尔数组和量程寄存器的长度必须相等。