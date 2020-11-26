---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202917"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


根据变量的数量，根据布尔值数组调整事实数据表

返回长度为的新数组 `2^numVars` ，可能要求 `table` 使用条目扩展大小或将 `false` 其截断到 `2^numVars` 元素。

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>输入

### <a name="table--bool"></a>table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

事实数据表作为真值数组


### <a name="numvars--int"></a>numVars： [Int](xref:microsoft.quantum.lang-ref.int)

变量数



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

调整大小的事实数据表