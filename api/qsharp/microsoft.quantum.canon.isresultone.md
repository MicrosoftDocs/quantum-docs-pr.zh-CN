---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: f259c21e6cc0a4886332e9ffcb546e527ec7def1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840330"
---
# <a name="isresultone-function"></a>IsResultOne 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


测试给定结果值是否等于 `One` 。

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a>输入

### <a name="input--__invalidresult__"></a>输入：__无效 <Result>__

`Result` 要测试的值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

如果等于，则返回 `true` `input` `One` 。