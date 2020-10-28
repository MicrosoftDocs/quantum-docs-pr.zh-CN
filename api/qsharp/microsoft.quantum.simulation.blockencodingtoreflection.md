---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700165"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


将转换为 `BlockEncoding` 等效的 `BLockEncodingReflection` 。

也就是说，假设有一个 `BlockEncoding` 用于对某个运算符进行编码的单一 $U $ $H $ 相关，则将其转换为对 `BlockEncodingReflection` 同一运算符进行编码的 $U $，同时满足 $U "^ \Dagger = U" $。
这会将 $U $ 的辅助寄存器大小增加了一个 qubit。

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>输入

### <a name="blockencoding--blockencoding"></a>blockEncoding： [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

`BlockEncoding`要转换为反射的单一 $U $。



## <a name="output--blockencodingreflection"></a>输出： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

单一 $U ' $ 共同操作寄存器并对 `a` 其 `s` 进行块编码 $H $，并满足 $U ^ \Dagger = U ' $。

## <a name="remarks"></a>注解

这会将 $U $ 的辅助寄存器大小增加了一个 qubit。

## <a name="references"></a>参考

- Hamiltonian 模拟 by Qubitization Guang 脱离 Hao Low、Isaac 语 https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>另请参阅

- [BlockEncoding。](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)