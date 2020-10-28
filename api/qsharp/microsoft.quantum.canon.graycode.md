---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696053"
---
# <a name="graycode-function"></a>GrayCode 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


创建灰色代码序列

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>输入

### <a name="n--int"></a>n： [Int](xref:microsoft.quantum.lang-ref.int)

位数



## <a name="output--intint"></a>Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []

元组的数组。 元组中的第一个值为 GrayCode 中的值。元组中的第二个值是要在当前值中更改以获取下一项的位置