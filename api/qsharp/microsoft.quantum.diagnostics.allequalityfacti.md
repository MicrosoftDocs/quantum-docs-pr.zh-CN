---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223878"
---
# <a name="allequalityfacti-function"></a>AllEqualityFactI 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言整数值的两个数组相等。

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--int"></a>实际： [Int](xref:microsoft.quantum.lang-ref.int)[]

由相关测试用例生成的数组。


### <a name="expected--int"></a>应为： [Int](xref:microsoft.quantum.lang-ref.int)[]

需要从相关测试用例进行计算的数组。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

如果数组不相等，则为要打印的消息。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

