---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701077"
---
# <a name="applytransposition-operation"></a>ApplyTransposition 操作

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

此操作将索引中的波幅替换 `a` 为 `b` 长度为 $n $ 的给定状态向量的索引中的波幅 `register` 。  如果 `a` 等于 `b` ，则不更改状态向量。

## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

第一个索引 (的值必须介于0到 $ 2 ^ n-$1) 


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

第二个索引 (的值必须介于0到 $ 2 ^ n-$1) 


### <a name="qubits--littleendian"></a>qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要向其应用调换的 $n $ qubits 的列表。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

