---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 59451b4f5c992f900a27139332059af7427b9b93
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696574"
---
# <a name="ripplecarryaddernocarryttk-operation"></a>RippleCarryAdderNoCarryTTK 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


可逆的就地波纹，无需执行即可额外添加两个整数。

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

给定两 $n 个在 LittleEndian 注册和中编码的 $ bit 整数， `xs` `ys` 操作将计算两个整数的总和： $ 2 ^ n $，其中 $n $ 是输入和的位大小 `xs` `ys` 。 它不计算执行位。

## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register 第一个整数被加数编码。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit register 编码为第二个整数被加数，将进行修改以容纳总和的 $n $ 最高有效位。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

此操作具有与 RippleCarryAdderTTK 相同的功能，但不会返回带有位。

## <a name="references"></a>参考

- Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro： "量程加法线路和无限制扇出"、量程信息和计算、2010。
  https://arxiv.org/abs/0910.2530