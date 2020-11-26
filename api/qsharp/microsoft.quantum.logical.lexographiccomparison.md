---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197578"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定比较函数，将返回 lexographically 比较两个数组的新函数。

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>输入

### <a name="elementcomparison--tt---bool"></a>elementComparison： ( t，不) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值

一个函数，它比较两个元素 `x` ，并 `y` 在 `x` 小于或等于时返回 `y` 。



## <a name="output--tt---bool"></a>输出： ( t []，t [] ) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值

一个函数，它比较两个数组 `xs` ， `ys` 并 `xs` `ys` 在 lexographical 排序之前或等于时返回。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要比较的数组元素的类型。

## <a name="remarks"></a>备注

两个数组之间的 lexographic 比较 `xs` ， `ys` 由以下过程定义。 假设 and 都为 true，则这两个元素 `x` 和 `y` 都是等效的 `elementComparison(x, y)` `elementComparison(y, x)` 。

- 这两个数组都是逐个元素进行比较，直到第一对不等效的元素。 如果数组包含首先按照 lexographical 排序发生的元素，则该数组将 `elementComparison` 首先出现。
- 如果未找到任何 inequivalent 的元素，并且一个数组的长度超过另一个，则认为较短的数组将首先出现。

## <a name="see-also"></a>另请参阅

- [已排序的](xref:Microsoft.Quantum.Arrays.Sorted)