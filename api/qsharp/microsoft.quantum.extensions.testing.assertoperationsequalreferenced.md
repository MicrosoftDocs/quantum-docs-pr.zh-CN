---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualReferenced has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 2d39f74c68e48d2f2b8003b76885c9444056f8d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695404"
---
# <a name="assertoperationsequalreferenced-operation"></a>AssertOperationsEqualReferenced 操作

命名空间： [Microsoft.](xref:Microsoft.Quantum.Extensions.Testing)

软件包 [](https://nuget.org/packages/)


> [!WARNING]
> AssertOperationsEqualReferenced 已被弃用。 请改用 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced>。
>
> 请使用 @"microsoft.quantum.diagnostics.assertoperationsequalreferenced"。
> 请注意，此操作的参数顺序已更改。



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a>输入

### <a name="actual--qubit--unit"></a>实际： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 




### <a name="expected--qubit--unit-adj"></a>应为： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词




### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

