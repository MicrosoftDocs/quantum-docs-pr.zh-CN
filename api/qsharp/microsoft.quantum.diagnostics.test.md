---
uid: Microsoft.Quantum.Diagnostics.Test
title: 测试用户定义类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 80821cb46d773d84085838d9ee539a8a45c43e61
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201489"
---
# <a name="test-user-defined-type"></a>测试用户定义类型

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


编译器可识别的属性，用于标记单元测试。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>命名项

### <a name="executiontarget--string"></a>ExecutionTarget： [字符串](xref:microsoft.quantum.lang-ref.string)

