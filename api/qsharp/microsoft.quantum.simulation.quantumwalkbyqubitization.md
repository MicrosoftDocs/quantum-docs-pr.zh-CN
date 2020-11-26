---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ccef1bbf400e01800053777d0010acb7addaef53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192479"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将块编码反射转换为量程审核。

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>描述

给定一个 `BlockEncodingReflection` 由单一 $U $ 表示的，用来对某个运算符 $H $ 相关的运算符进行编码，并将其转换为量程审核 $W $，其中包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的范围。

## <a name="input"></a>输入

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`要转换为量程审核的单一 $U $。



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

量程审核 $W $ 联合在寄存器上， `a` 并对 `s` $H $ 进行阻止编码，并包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的范围。

## <a name="references"></a>参考

- Hamiltonian 模拟 by Qubitization Guang 脱离 Hao Low、Isaac 语 https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>另请参阅

- [BlockEncoding。](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)