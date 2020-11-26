---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 273692efa629cb8cc20069ef500c4e0902fbc3ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201336"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>_ExtractLogicalQubitFromSteaneCode 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


与嵌入有关的症状。

不会平等对待 $X $-和 $Z $-stabilizers，这是因为编码线路的特定选择。
这种不对称会导致不同的症状提取例程。
可以通过直接在代码状态上测量多 qubit Pauli 运算符来度量症状，但对于升华目的，逻辑 qubit 将返回到单个 qubit 中，而无需进一步 ancillas。

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>输入

### <a name="code--logicalregister"></a>代码： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) 

逻辑 qubit 和一对整数，用于 $X $-症状和 $Z $-症状。
它们表示代码 qubit 的索引，其中一次 $X $ 或 $Z $-错误将导致测定的症状。

## <a name="remarks"></a>备注

请注意，此操作不会标记为 `internal` ，因为单元测试直接依赖于此操作。 作为未来的改进，应重构单元测试，使其仅依赖公共 callables。

> [!WARNING]
> 对于 Steane 的 7 qubit 代码，此例程定制为特定的编码线路;如果修改了编码线路，则可能必须以不同的方式解释症状结果。