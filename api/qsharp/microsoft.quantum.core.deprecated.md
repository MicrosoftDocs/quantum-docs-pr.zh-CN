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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="c4c23-102">不推荐使用的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="c4c23-102">Deprecated user defined type</span></span>

<span data-ttu-id="c4c23-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="c4c23-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="c4c23-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c4c23-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c4c23-105">编译器可识别的属性，用于将类型或可调用标记为已弃用。</span><span class="sxs-lookup"><span data-stu-id="c4c23-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="c4c23-106">命名项</span><span class="sxs-lookup"><span data-stu-id="c4c23-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="c4c23-107">NewName： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c4c23-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c4c23-108">要改用的类型的完整名称或可调用的。</span><span class="sxs-lookup"><span data-stu-id="c4c23-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="c4c23-109">如果在不替换的情况下已弃用类型或可调用，则将设置为空字符串。</span><span class="sxs-lookup"><span data-stu-id="c4c23-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>