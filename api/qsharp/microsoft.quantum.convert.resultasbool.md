---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 34fca15faf79f706b398e3fdfc537ea91b28da86
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695650"
---
# <a name="resultasbool-function"></a>ResultAsBool 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

软件包 [](https://nuget.org/packages/)


将 `Result` 类型转换为 `Bool` 类型，其中 `One` 映射到 `true` 并 `Zero` 映射到 `false` 。

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a>输入

### <a name="input--__invalidresult__"></a>输入： __无效 <Result>__

`Result` 要转换的。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

表示 `input` 的 `Bool`。