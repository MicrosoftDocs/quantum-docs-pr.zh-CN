---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 47e8a74d3631be2209537679ec9786a8dab63c58
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200775"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个函数，该函数通过表查找⟦5，1，3⟧量程代码，将错误症状度量映射到相应的纠错 Pauli 运算符。

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>输出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

采用症状度量的类型的函数 `RecoveryFn` `Result[]` ，并返回 `Pauli[]` 更正检测到的错误的运算符。

## <a name="remarks"></a>备注

通过循环访问权重 $1 $ 的所有错误，我们获取总计 $ 3 \ 乘以 5 = 15 $ 可能的非普通 syndromes。
除了标识，还生成了一个错误表和相应的症状。 对于5个 qubit 代码，此表由提供： $X \_ 1： (0，0，0，1) ;X \_ 2： (1，0，0，0) ;X \_ 3： (1，1，0，0) ;X \_ 4： (0，1，1，0) ;X \_ 5： (0，0，1，1) $，$Z \_ 1： (1，0，1，0) ;Z \_ 2： (0，1，0，1) ;Z \_ 3： (0，0，1，0) ;Z \_ 4： (1，0，0，1) ;Z \_ 5： (0、1、0、0) $ $Y 通过添加 $X _i $ 和 $Z _i $ syndromes 获取 _i $。 请注意，表查找恢复中的排序通过使用 little endian) 将 bitvectors 转换为整数 (提供。

## <a name="see-also"></a>另请参阅

- [ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)