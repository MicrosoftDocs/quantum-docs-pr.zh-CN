---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824404"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对于给定的 qubits 寄存器上的 Pauli 操作表，此函数返回一个类型为的对象，该对象 `RecoveryFn` 包含对给定的 Pauli 操作数组执行表查找解码所需的所有信息。

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>输入

### <a name="table--pauli"></a>table： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

在给定的 qubit 注册上操作的 Pauli 操作表



## <a name="output--recoveryfn"></a>输出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

类型为的对象 `RecoveryFn` ，即， `Syndrome -> Pauli[]` 与给定症状数组关联的映射对应 Pauli 更正操作。