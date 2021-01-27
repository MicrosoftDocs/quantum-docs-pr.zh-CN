---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853659"
---
# <a name="rangereverse-function"></a>RangeReverse 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回一个新范围，该范围是输入范围的反向。

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>输入

### <a name="r--range"></a>r： [范围](xref:microsoft.quantum.lang-ref.range)

输入范围。



## <a name="output--range"></a>输出： [范围](xref:microsoft.quantum.lang-ref.range)

与给定范围相反的新范围。

## <a name="remarks"></a>备注

请注意，范围的反向不只是 `end` ... `-step` `start` ，因为范围的实际最后一个元素可能与相同 `end` 。