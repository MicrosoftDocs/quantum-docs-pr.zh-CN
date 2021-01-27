---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855199"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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