---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3cf09e48cce1aeb1aac837465ee3a5e06adf5169
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851007"
---
# <a name="sequencei-function"></a>SequenceI 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

```qsharp
let arr1 = SequenceI(0, 3); // [0, 1, 2, 3]
let arr2 = SequenceI(23, 29); // [23, 24, 25, 26, 27, 28, 29]
let arr3 = SequenceI(-5, -2); // [-5, -4, -3, -2]

let numbers = SequenceI(0, _); // function to create sequence from 0 to `to`
let naturals = SequenceI(1, _); // function to create sequence from 1 to `to`
```