---
uid: Microsoft.Quantum.Arrays.Partitioned
title: 分区函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845546"
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



## <a name="example"></a>示例

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```