---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850592"
---
# <a name="applytomost-operation"></a>ApplyToMost 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将操作应用到数组中除最后一个元素之外的所有元素。

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>说明

给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。

## <a name="input"></a>输入

### <a name="op--t--unit"></a>op： t [] => [单元](xref:microsoft.quantum.lang-ref.unit) 

要应用的操作。


### <a name="targets--t"></a>目标： t []

目标的数组，其中除最后一个外的所有将应用于 `op` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要应用的操作的输入类型。

## <a name="example"></a>示例

以下 Q # 代码段是等效的：

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)