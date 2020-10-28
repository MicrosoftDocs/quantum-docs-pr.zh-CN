---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700181"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU 操作

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


`BlockEncodingByLCU` 的实现。

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>输入

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl




### <a name="selector--ts--unit-adj--ctl"></a>选择器： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl




### <a name="auxiliary--t"></a>辅助：不




### <a name="system--s"></a>系统：的





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="s"></a>我们

