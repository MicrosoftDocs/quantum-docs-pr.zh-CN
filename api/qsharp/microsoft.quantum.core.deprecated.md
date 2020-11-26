---
uid: Microsoft.Quantum.Core.Deprecated
title: 不推荐使用的用户定义类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224082"
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