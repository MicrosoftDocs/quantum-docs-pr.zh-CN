---
uid: Microsoft.Quantum.Arrays.Chunks
title: 区块函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696555"
---
# <a name="chunks-function"></a>区块函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


将数组拆分为长度相等的多个部分。

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>输入

### <a name="nelements--int"></a>nElements： [Int](xref:microsoft.quantum.lang-ref.int)

每个区块的长度。


### <a name="arr--t"></a>arr： t []

要拆分的数组。



## <a name="output--t"></a>输出： t [] []

包含原始数组的每个块的数组。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>注解

请注意，输出的最后一个元素可能比不能被整除的更短 `nElements` `Length(arr)` `nElements` 。