---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696037"
---
# <a name="isresultone-function"></a>IsResultOne 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


测试给定结果值是否等于 `One` 。

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a>输入

### <a name="input--__invalidresult__"></a>输入： __无效 <Result>__

`Result` 要测试的值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

如果等于，则返回 `true` `input` `One` 。