---
uid: Microsoft.Quantum.Core.Deprecated
title: 不推荐使用的用户定义类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832084"
---
# <a name="deprecated-user-defined-type"></a>不推荐使用的用户定义类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


编译器可识别的属性，用于将类型或可调用标记为已弃用。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>命名项

### <a name="newname--string"></a>NewName： [String](xref:microsoft.quantum.lang-ref.string)

要改用的类型的完整名称或可调用的。
如果在不替换的情况下已弃用类型或可调用，则将设置为空字符串。