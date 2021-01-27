---
uid: Microsoft.Quantum.Bitwise.Not
title: Not 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842116"
---
# <a name="not-function"></a>Not 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回整数的按位 "非"。
这会执行与内置运算符相同的计算 `~~~` 。

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>示例

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a>备注

有关更多详细信息，请参阅 [c # ~ 运算符](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) 。