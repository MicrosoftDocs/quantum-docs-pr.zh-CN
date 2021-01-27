---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834194"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将 `Bool[]` 类型转换为 `Result[]` 类型，其中 `true` 映射到 `One` 并 `false` 映射到 `Zero` 。

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>输入

### <a name="input--bool"></a>输入： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` 要转换的。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__[]

表示 `input` 的 `Result[]`。