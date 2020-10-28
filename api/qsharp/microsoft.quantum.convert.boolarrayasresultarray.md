---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695686"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

软件包 [](https://nuget.org/packages/)


将 `Bool[]` 类型转换为 `Result[]` 类型，其中 `true` 映射到 `One` 并 `false` 映射到 `Zero` 。

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>输入

### <a name="input--bool"></a>输入： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` 要转换的。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__ []

表示 `input` 的 `Result[]`。