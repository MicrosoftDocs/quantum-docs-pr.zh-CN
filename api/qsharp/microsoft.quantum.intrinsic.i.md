---
uid: Microsoft.Quantum.Intrinsic.I
title: 我的操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 0af14a9aff20da493e95c7feba6afbb907d3d69f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849410"
---
# <a name="i-operation"></a>我的操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


在单个 qubit 上执行不含 op)  (的标识操作。

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

这是一个不能操作的。 提供此方法是为了提供完整的，因为有时在算法中调用标识或将其作为参数传递是非常有用的。