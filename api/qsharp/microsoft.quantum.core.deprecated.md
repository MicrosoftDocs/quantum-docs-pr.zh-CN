---
uid: Microsoft.Quantum.Core.Deprecated
title: 不推荐使用的用户定义类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695640"
---
# <a name="deprecated-user-defined-type"></a>不推荐使用的用户定义类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)

软件包 [](https://nuget.org/packages/)


编译器可识别的属性，用于将类型或可调用标记为已弃用。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>命名项

### <a name="newname--string"></a>NewName： [String](xref:microsoft.quantum.lang-ref.string)

要改用的类型的完整名称或可调用的。
如果在不替换的情况下已弃用类型或可调用，则将设置为空字符串。