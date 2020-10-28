---
uid: Microsoft.Quantum.Intrinsic.I
title: 我的操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 555f714047a38f49ccd94a77dc14a46d6f4988ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696648"
---
# <a name="i-operation"></a>我的操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


在单个 qubit 上执行不含 op)  (的标识操作。

```qsharp
operation I (target : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

这是一个不能操作的。 提供此方法是为了提供完整的，因为有时在算法中调用标识或将其作为参数传递是非常有用的。