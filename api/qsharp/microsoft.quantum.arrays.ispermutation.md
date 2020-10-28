---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696495"
---
# <a name="ispermutation-function"></a>IsPermutation 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


当且仅当给定数组表示排列时，输出为 true。

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>说明

给定 `array` 长度的数组 `n` ，当且仅当中的每个整数仅出现一次时，才返回 true， `0` 这样就 `n - 1` `array` `array` 可以解释为元素上的排列方式 `n` 。

## <a name="input"></a>输入

### <a name="permuation--int"></a>permuation： [Int](xref:microsoft.quantum.lang-ref.int)[]

一个数组，该数组可以是也可以不表示排列。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值



## <a name="remarks"></a>注解

长度为零的数组是完全的。