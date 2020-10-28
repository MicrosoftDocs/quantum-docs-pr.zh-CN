---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 8bbd4af0389a7b748be11dc50bacd2c178521adc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700897"
---
# <a name="_jwoptimizedz-operation"></a>_JWOptimizedZ 操作

命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)

软件包 [](https://nuget.org/packages/)


应用 Vny-rz-j42 旋转，在阶段估算中使用 C-NOT 技巧到双相位。

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="angle--double"></a>angle： [Double](xref:microsoft.quantum.lang-ref.double)

旋转的 Vny-rz-j42 角度。


### <a name="parityqubit--qubit"></a>parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit，用于确定时间演化的符号。


### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

