---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 95364541adfa1dc57b1f147c3992c9fd9f5f6c68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201557"
---
# <a name="nearequalityfactcp-function"></a><span data-ttu-id="d0a05-102">NearEqualityFactCP 函数</span><span class="sxs-lookup"><span data-stu-id="d0a05-102">NearEqualityFactCP function</span></span>

<span data-ttu-id="d0a05-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d0a05-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d0a05-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0a05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0a05-105">断言传统复数的预期值为小公差 1e-10。</span><span class="sxs-lookup"><span data-stu-id="d0a05-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a><span data-ttu-id="d0a05-106">输入</span><span class="sxs-lookup"><span data-stu-id="d0a05-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="d0a05-107">实际： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="d0a05-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="d0a05-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="d0a05-108">The number to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="d0a05-109">应为： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="d0a05-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="d0a05-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="d0a05-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0a05-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0a05-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

