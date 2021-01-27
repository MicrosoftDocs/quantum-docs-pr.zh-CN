---
uid: Microsoft.Quantum.Bitwise.Or
title: Or 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Or
qsharp.summary: Returns the bitwise OR of two integers. This performs the same computation as the built-in `|||` operator.
ms.openlocfilehash: 811e7cf64424e8302c5745c4c71d76de50ab8c08
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845266"
---
# <a name="or-function"></a>Or 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回两个整数的按位 "或"。
这会执行与内置运算符相同的计算 `|||` 。

```qsharp
function Or (a : Int, b : Int) : Int
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>示例

```qsharp
let a = 248;      //                 11111000₂
let b = 63;       //                 00111111₂
let x = Or(a, b); // x : Int = 255 = 11111111₂.
```

## <a name="remarks"></a>备注

请参阅 [c # |运算符](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) 了解更多详细信息。