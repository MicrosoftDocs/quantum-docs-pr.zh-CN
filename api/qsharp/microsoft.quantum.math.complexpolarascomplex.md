---
uid: Microsoft.Quantum.Math.ComplexPolarAsComplex
title: ComplexPolarAsComplex 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolarAsComplex
qsharp.summary: Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.
ms.openlocfilehash: ace458ec168b70a873fae2a4990b9a427efac7cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228604"
---
# <a name="complexpolarascomplex-function"></a><span data-ttu-id="043bb-102">ComplexPolarAsComplex 函数</span><span class="sxs-lookup"><span data-stu-id="043bb-102">ComplexPolarAsComplex function</span></span>

<span data-ttu-id="043bb-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="043bb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="043bb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="043bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="043bb-105">将类型的复杂数字转换 `ComplexPolar` 为类型的复数 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="043bb-105">Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.</span></span>

```qsharp
function ComplexPolarAsComplex (input : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a><span data-ttu-id="043bb-106">输入</span><span class="sxs-lookup"><span data-stu-id="043bb-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="043bb-107">输入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="043bb-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="043bb-108">复数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="043bb-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--complex"></a><span data-ttu-id="043bb-109">输出： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="043bb-109">Output : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="043bb-110">复数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="043bb-110">Complex number $c = x + i y$.</span></span>