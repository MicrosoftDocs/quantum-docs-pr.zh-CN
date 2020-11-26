---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解压缩函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219951"
---
# <a name="unzipped-function"></a>解压缩函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定一个2元组数组，返回两个数组的元组，其中每个数组包含输入数组的元组的元素。

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>输入

### <a name="arr--tu"></a>arr： ( ' U) []

包含2元组的数组



## <a name="output--tu"></a>Output： ( t []，' U [] ) 

两个数组，第一个数组包含输入元组的所有第一个元素，第二个数组包含输入元组的所有第二个元素。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个元组中第一个元素的类型
### <a name="u"></a>' U

每个元组中第二个元素的类型

## <a name="see-also"></a>另请参阅

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)