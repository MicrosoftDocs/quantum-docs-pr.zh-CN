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
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="6ad2f-102">不推荐使用的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="6ad2f-102">Deprecated user defined type</span></span>

<span data-ttu-id="6ad2f-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="6ad2f-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="6ad2f-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6ad2f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6ad2f-105">编译器可识别的属性，用于将类型或可调用标记为已弃用。</span><span class="sxs-lookup"><span data-stu-id="6ad2f-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="6ad2f-106">命名项</span><span class="sxs-lookup"><span data-stu-id="6ad2f-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="6ad2f-107">NewName： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6ad2f-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6ad2f-108">要改用的类型的完整名称或可调用的。</span><span class="sxs-lookup"><span data-stu-id="6ad2f-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="6ad2f-109">如果在不替换的情况下已弃用类型或可调用，则将设置为空字符串。</span><span class="sxs-lookup"><span data-stu-id="6ad2f-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>