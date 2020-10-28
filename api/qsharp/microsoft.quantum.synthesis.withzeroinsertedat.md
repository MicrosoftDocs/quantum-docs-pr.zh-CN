---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701048"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


将0位插入到整数中

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>说明

此操作采用一个整数，插入0位 `position` ，并将更新后的值作为整数返回。  例如，在第2个 (¥10 _ = 1010_ $) 的位置2处插入0将 {10} {2} 返回数字 18 ($18 _ {10} = 10010_ {2} $) 。

## <a name="input"></a>输入

### <a name="position--int"></a>位置： [Int](xref:microsoft.quantum.lang-ref.int)

插入0的位置


### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

修改的值



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

修改的值