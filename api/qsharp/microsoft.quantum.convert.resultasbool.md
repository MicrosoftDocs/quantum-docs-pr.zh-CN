---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: a170acf635e4e2b2150ffc208fabc9782ff837b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224167"
---
# <a name="resultasbool-function"></a>ResultAsBool 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将 `Result` 类型转换为 `Bool` 类型，其中 `One` 映射到 `true` 并 `Zero` 映射到 `false` 。

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a>输入

### <a name="input--__invalidresult__"></a>输入：__无效 <Result>__

`Result` 要转换的。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

表示 `input` 的 `Bool`。