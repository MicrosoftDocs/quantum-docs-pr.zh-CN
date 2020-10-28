---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解压缩函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696442"
---
# <a name="unzipped-function"></a>解压缩函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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