---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840496"
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

## <a name="example"></a>示例

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```