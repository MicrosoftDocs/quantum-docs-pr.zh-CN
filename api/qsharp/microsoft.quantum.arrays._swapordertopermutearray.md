---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696559"
---
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


返回数组中的 order 元素需要进行交换，以生成有序的数组。
假设发生了交换。

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>输入

### <a name="neworder--int"></a>newOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]

数组，其中包含新数组的索引。 应该存在 $n $ 个元素，每个元素都是 $0 $ 到 $n-$1 的唯一整数。



## <a name="output--intint"></a>Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []

元组表示要交换的两个索引。 交换从最低索引开始。

## <a name="remarks"></a>注解

## <a name="psuedocode"></a>Psuedocode

对于 0.. Length 中的 (索引 (newOrder) -1) {while newOrder [index]！ = index {Switch newOrder [index] with newOrder [newOrder [index]]}}