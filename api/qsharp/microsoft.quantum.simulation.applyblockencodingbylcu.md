---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852823"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU 操作

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


`BlockEncodingByLCU` 的实现。

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl




### <a name="selector--ts--unit--is-adj--ctl"></a>选择器： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit)  为调整 + Ctl




### <a name="auxiliary--t"></a>辅助：不




### <a name="system--s"></a>系统：的





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="s"></a>我们

