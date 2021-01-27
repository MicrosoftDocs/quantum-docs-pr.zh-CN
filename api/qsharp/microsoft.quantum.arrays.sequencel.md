---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850992"
---
# <a name="sequencel-function"></a>SequenceL 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>备注

与之间的 `from` 差异 `to` 必须符合某个 `Int` 值。