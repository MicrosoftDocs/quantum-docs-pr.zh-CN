---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701032"
---
# <a name="modulusl-function"></a>ModulusL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


计算模的规范 residue `value` `modulus` 。

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>输入

### <a name="value--bigint"></a>值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

计算 residue 的值


### <a name="modulus--bigint"></a>模数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Residues 所采用的模数必须为正数



## <a name="output--bigint"></a>输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

0之间的整数 $r $， `modulus - 1` 这可 `value - r` 被模数整除

## <a name="remarks"></a>注解

此函数的行为方式与运算符 `%` 在 c # 和 Q # 中的行为方式相同，因为结果中始终是一个介于0到之间的正整数 `modulus - 1` ，即使值为负。