---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194825"
---
# <a name="plusa-function"></a>PlusA 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回两个输入 (串联) 的总和。

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a>输入

### <a name="a--element"></a>a： ' Element []

要求和 $a $ 的第一个输入。


### <a name="b--element"></a>b： "Element []

要求和 $b $ 的第二个输入。



## <a name="output--element"></a>Output： "Element []

Sum $a + b $。

## <a name="type-parameters"></a>类型参数

### <a name="element"></a>' 元素

两个输入数组中每个元素的类型。