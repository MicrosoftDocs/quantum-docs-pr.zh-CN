---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204124"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="76f91-102">HTerm 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="76f91-102">HTerm user defined type</span></span>

<span data-ttu-id="76f91-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="76f91-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="76f91-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="76f91-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="76f91-105">从 c # 传递到 Q # 以表示 Hamiltonian 的术语的数据格式。</span><span class="sxs-lookup"><span data-stu-id="76f91-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="76f91-106">表示的数据的含义取决于接收数据的算法。</span><span class="sxs-lookup"><span data-stu-id="76f91-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

