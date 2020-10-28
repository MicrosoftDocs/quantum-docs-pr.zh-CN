---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700412"
---
# <a name="quantumromqubitcount-function"></a>QuantumROMQubitCount 函数

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

软件包 [](https://nuget.org/packages/)


返回必须分配给返回的操作的 qubits 的总数 `QuantumROM` 。

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>输入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目标错误 $ \epsilon $。


### <a name="ncoeffs--int"></a>nCoeffs： [Int](xref:microsoft.quantum.lang-ref.int)

在中指定的系数数 `QuantumROM` 。



## <a name="output--intintint"></a>Output： ([int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) # A3

## <a name="first-parameter"></a>第一个参数

一个元组， `(x,(y,z))` 其中 `x = y + z` 是所分配的 qubits 总数， `y` 是寄存器的 qubits 数 `LittleEndian` ， `z` 是垃圾 qubits 的数目。