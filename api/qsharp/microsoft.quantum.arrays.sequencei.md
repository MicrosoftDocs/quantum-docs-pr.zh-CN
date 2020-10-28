---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696460"
---
# <a name="sequencei-function"></a>SequenceI 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


获取给定时间间隔内的整数数组。

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>输入

### <a name="from--int"></a>起始： [Int](xref:microsoft.quantum.lang-ref.int)

间隔的包含开始索引。


### <a name="to--int"></a>to： [Int](xref:microsoft.quantum.lang-ref.int)

不小于的间隔的非独占结束索引 `from` 。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

一个包含数字序列的数组， `from` `from + 1` ，...， `to` 。