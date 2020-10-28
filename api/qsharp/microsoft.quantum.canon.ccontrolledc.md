---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696112"
---
# <a name="ccontrolledc-function"></a>CControlledC 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。 如果为，则不 `false` 执行任何操作。
修饰符 `C` 指示操作可控制。

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>输入

### <a name="op--t--unit-ctl"></a>op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl

要有条件地应用的操作。



## <a name="output--boolt--unit-ctl"></a>Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

如果经典控制位为 true，则为 op 的新操作。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要有条件地应用的操作的输入类型。

## <a name="see-also"></a>另请参阅

- [Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)