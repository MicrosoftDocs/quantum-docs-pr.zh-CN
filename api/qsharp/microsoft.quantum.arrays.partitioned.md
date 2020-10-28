---
uid: Microsoft.Quantum.Arrays.Partitioned
title: 分区函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696473"
---
# <a name="partitioned-function"></a>分区函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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

