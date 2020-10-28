---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696136"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


根据索引排列 control、target 和 helper qubits

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>说明

返回一个 Qubit 数组，其目标位于索引0，并在索引 2 ^ i 处控制 i。  帮助器 qubits 将被插入到数组中的其他所有位置。

## <a name="input"></a>输入

### <a name="controls--qubit"></a>控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>helper： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

