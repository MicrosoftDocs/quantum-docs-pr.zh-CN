---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842705"
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