---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696457"
---
# <a name="sequencel-function"></a>SequenceL 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


获取给定时间间隔内的整数数组。

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>输入

### <a name="from--bigint"></a>from： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

间隔的包含开始索引。


### <a name="to--bigint"></a>to： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

不小于的间隔的非独占结束索引 `from` 。



## <a name="output--bigint"></a>输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]

一个包含数字序列的数组， `from` `from + 1` ，...， `to` 。

## <a name="remarks"></a>注解

与之间的 `from` 差异 `to` 必须符合某个 `Int` 值。