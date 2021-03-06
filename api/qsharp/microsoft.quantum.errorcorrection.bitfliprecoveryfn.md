---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: 1cf2bd944b4dcaadeeca96fa0f576250590962e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827603"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


针对⟦3，1，1⟧位翻转代码的表查找，针对给定的症状度量的恢复 Pauli 操作的函数。

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>输出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`采用症状度量 `Result[]` 并返回 `Pauli[]` 更正检测到的错误的操作的类型的函数。

## <a name="see-also"></a>另请参阅

- [ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)