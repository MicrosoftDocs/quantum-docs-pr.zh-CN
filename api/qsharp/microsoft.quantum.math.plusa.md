---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695116"
---
# <a name="plusa-function"></a>PlusA 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


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