---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: RippleCarryAdderTTK 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 5366ace36e63d361a439bfc5a1a78fdf9a353062
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696571"
---
# <a name="ripplecarryadderttk-operation"></a>RippleCarryAdderTTK 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


可逆的就地波纹-包含两个整数。
假设在 LittleEndian 中编码的两个 $n $ 位整数 `xs` 和 `ys` 一个 qubit，则该操作将计算两个整数的总和，其中包含结果的 $n $ 最低有效位 `ys` ，而执行位被 xored 到 qubit `carry` 。

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register 第一个整数被加数编码。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register 编码为第二个整数被加数，将进行修改以容纳总和的 $n $ 最高有效位。


### <a name="carry--qubit"></a>携带： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

携带 qubit，是 xored，其最高有效位是 sum。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

此操作与 RippleCarryAdderD 和 RippleCarryAdderCDKM 具有相同的功能，但不使用任何 ancilla qubits。

## <a name="references"></a>参考

- Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro： "量程加法线路和无限制扇出"、量程信息和计算、2010。
  https://arxiv.org/abs/0910.2530