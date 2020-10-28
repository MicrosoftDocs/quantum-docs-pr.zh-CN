---
uid: Microsoft.Quantum.Arrays.Swapped
title: 交换函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696448"
---
# <a name="swapped-function"></a>交换函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


应用数组中两个元素的交换。

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="firstindex--int"></a>firstIndex： [Int](xref:microsoft.quantum.lang-ref.int)

要交换的第一个元素的索引。


### <a name="secondindex--int"></a>secondIndex： [Int](xref:microsoft.quantum.lang-ref.int)

要交换的第二个元素的索引。


### <a name="arr--t"></a>arr： t []

包含要交换的元素的数组。



## <a name="output--t"></a>输出： t []

应用了就地交换的数组。

## <a name="example"></a>示例

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

