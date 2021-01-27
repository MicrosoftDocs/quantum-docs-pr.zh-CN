---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847347"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="2aa42-102">ComplexPolar 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="2aa42-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="2aa42-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2aa42-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2aa42-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2aa42-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2aa42-105">表示极坐标形式的复数。</span><span class="sxs-lookup"><span data-stu-id="2aa42-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="2aa42-106">复数的极坐标表示形式为 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="2aa42-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="2aa42-107">命名项</span><span class="sxs-lookup"><span data-stu-id="2aa42-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="2aa42-108">数量级： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2aa42-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2aa42-109">$C $ $r \ge $0 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="2aa42-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="2aa42-110">参数： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2aa42-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2aa42-111">$C $ 的 \in \mathbb R $ $t 阶段。</span><span class="sxs-lookup"><span data-stu-id="2aa42-111">The phase $t \in \mathbb R$ of $c$.</span></span>