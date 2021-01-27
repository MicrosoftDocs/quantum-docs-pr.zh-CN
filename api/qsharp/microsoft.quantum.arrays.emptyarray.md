---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: 此时函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846175"
---
# <a name="emptyarray-function"></a>此时函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


返回给定类型的空数组。

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>输出： "TElement []

空数组。

## <a name="type-parameters"></a>类型参数

### <a name="telement"></a>' TElement

数组元素的类型。

## <a name="example"></a>示例

```qsharp
let empty = EmptyArray<Int>();
```