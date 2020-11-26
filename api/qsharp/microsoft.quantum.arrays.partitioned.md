---
uid: Microsoft.Quantum.Arrays.Partitioned
title: 分区函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220495"
---
# <a name="partitioned-function"></a>分区函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将数组拆分为多个部分。

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>输入

### <a name="nelements--int"></a>nElements： [Int](xref:microsoft.quantum.lang-ref.int)[]

数组的每个部分中的元素数


### <a name="arr--t"></a>arr： t []

要拆分的输入数组。



## <a name="output--t"></a>输出： t [] []

多个数组，其中第一个数组是第一个数组 `nElements[0]` `arr` ，第二个数组 `nElements[1]` 是 `arr` 等。最后一个数组将包含所有剩余元素。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

