---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210975"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="90e24-102">ComplexPolar 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="90e24-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="90e24-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="90e24-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="90e24-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90e24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90e24-105">表示极坐标形式的复数。</span><span class="sxs-lookup"><span data-stu-id="90e24-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="90e24-106">复数的极坐标表示形式为 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="90e24-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="90e24-107">命名项</span><span class="sxs-lookup"><span data-stu-id="90e24-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="90e24-108">数量级： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90e24-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90e24-109">$C $ $r \ge $0 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="90e24-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="90e24-110">参数： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90e24-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90e24-111">$C $ 的 \in \mathbb R $ $t 阶段。</span><span class="sxs-lookup"><span data-stu-id="90e24-111">The phase $t \in \mathbb R$ of $c$.</span></span>