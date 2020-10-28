---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695294"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring 函数

命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)

软件包 [](https://nuget.org/packages/)


的传统处理步骤 `ApplyDeltaParity` 。
这会计算控制 qubits 的列表，用于评估任意两个 PQRS 之间的奇偶校验差异 .。。偶数的长度。

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>输入

### <a name="prevfermionicterm--int"></a>prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) 



## <a name="remarks"></a>注解

这假定字词的长度为偶数。
计算任意两个字词之间的奇偶校验差异的控件列表。
这假定输入列表按升序排序。