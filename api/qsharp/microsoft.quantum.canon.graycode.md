---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206878"
---
# <a name="graycode-function"></a>GrayCode 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


创建灰色代码序列

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>输入

### <a name="n--int"></a>n： [Int](xref:microsoft.quantum.lang-ref.int)

位数



## <a name="output--intint"></a>Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []

元组的数组。 元组中的第一个值为 GrayCode 中的值。元组中的第二个值是要在当前值中更改以获取下一项的位置