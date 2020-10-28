---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696114"
---
# <a name="ccontrolled-function"></a>CControlled 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。 如果为，则不 `false` 执行任何操作。

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>输入

### <a name="op--t--unit"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) 

要有条件地应用的操作。



## <a name="output--boolt--unit"></a>Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [单位](xref:microsoft.quantum.lang-ref.unit) 

如果经典控制位为 true，则为 op 的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要有条件地应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Canon. CControlledA](xref:Microsoft.Quantum.Canon.CControlledA)
- [Canon. CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)