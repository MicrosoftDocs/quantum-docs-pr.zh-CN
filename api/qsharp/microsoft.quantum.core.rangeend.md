---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695636"
---
# <a name="rangeend-function"></a>RangeEnd 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)

软件包 [](https://nuget.org/packages/)


返回给定范围的定义结束值，该范围不一定是序列中的最后一个元素。

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>输入

### <a name="range--range"></a>范围： [范围](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

给定范围的定义结束值。

## <a name="remarks"></a>注解

范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。

请注意，范围的定义结束值可以与范围指定的序列中的最后一个元素不同;例如，在0到1的范围内。 2.。 5最后一个元素为4，但结束值为5。