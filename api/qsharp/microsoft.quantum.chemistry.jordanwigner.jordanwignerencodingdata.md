---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData
title: JordanWignerEncodingData 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerEncodingData
qsharp.summary: Format of data passed from C# to Q# to represent all information for Hamiltonian simulation. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 62988eefa57d8a9e4ed9dcfbdbc6c3b630c6faa2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695751"
---
# <a name="jordanwignerencodingdata-user-defined-type"></a><span data-ttu-id="7105b-102">JordanWignerEncodingData 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="7105b-102">JordanWignerEncodingData user defined type</span></span>

<span data-ttu-id="7105b-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7105b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7105b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7105b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7105b-105">从 c # 传递到 Q # 以表示 Hamiltonian 模拟的所有信息的数据格式。</span><span class="sxs-lookup"><span data-stu-id="7105b-105">Format of data passed from C# to Q# to represent all information for Hamiltonian simulation.</span></span>
<span data-ttu-id="7105b-106">表示的数据的含义取决于接收数据的算法。</span><span class="sxs-lookup"><span data-stu-id="7105b-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerEncodingData = (Int, Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms, (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), Double);
```

