---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695122"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="82e7a-102">ComplexPolar 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="82e7a-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="82e7a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="82e7a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="82e7a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82e7a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82e7a-105">表示极坐标形式的复数。</span><span class="sxs-lookup"><span data-stu-id="82e7a-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="82e7a-106">复数的极坐标表示形式为 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="82e7a-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="82e7a-107">命名项</span><span class="sxs-lookup"><span data-stu-id="82e7a-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="82e7a-108">数量级： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="82e7a-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="82e7a-109">$C $ $r \ge $0 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="82e7a-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="82e7a-110">参数： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="82e7a-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="82e7a-111">$C $ 的 \in \mathbb R $ $t 阶段。</span><span class="sxs-lookup"><span data-stu-id="82e7a-111">The phase $t \in \mathbb R$ of $c$.</span></span>