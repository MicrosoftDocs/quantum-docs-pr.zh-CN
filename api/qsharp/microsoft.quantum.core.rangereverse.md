---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695634"
---
# <a name="rangereverse-function"></a>RangeReverse 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)

软件包 [](https://nuget.org/packages/)


返回一个新范围，该范围是输入范围的反向。

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>输入

### <a name="r--range"></a>r： [范围](xref:microsoft.quantum.lang-ref.range)

输入范围。



## <a name="output--range"></a>输出： [范围](xref:microsoft.quantum.lang-ref.range)

与给定范围相反的新范围。

## <a name="remarks"></a>注解

请注意，范围的反向不只是 `end` ... `-step` `start` ，因为范围的实际最后一个元素可能与相同 `end` 。