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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="9fae0-102">不推荐使用的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="9fae0-102">Deprecated user defined type</span></span>

<span data-ttu-id="9fae0-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="9fae0-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="9fae0-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fae0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9fae0-105">编译器可识别的属性，用于将类型或可调用标记为已弃用。</span><span class="sxs-lookup"><span data-stu-id="9fae0-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="9fae0-106">命名项</span><span class="sxs-lookup"><span data-stu-id="9fae0-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="9fae0-107">NewName： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9fae0-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9fae0-108">要改用的类型的完整名称或可调用的。</span><span class="sxs-lookup"><span data-stu-id="9fae0-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="9fae0-109">如果在不替换的情况下已弃用类型或可调用，则将设置为空字符串。</span><span class="sxs-lookup"><span data-stu-id="9fae0-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>