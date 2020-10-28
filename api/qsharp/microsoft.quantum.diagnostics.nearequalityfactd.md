---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695551"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="cb9ce-102">NearEqualityFactD 函数</span><span class="sxs-lookup"><span data-stu-id="cb9ce-102">NearEqualityFactD function</span></span>

<span data-ttu-id="cb9ce-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cb9ce-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cb9ce-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb9ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb9ce-105">断言传统浮点值的预期值为小公差 1e-10。</span><span class="sxs-lookup"><span data-stu-id="cb9ce-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="cb9ce-106">输入</span><span class="sxs-lookup"><span data-stu-id="cb9ce-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="cb9ce-107">实际： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb9ce-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cb9ce-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="cb9ce-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="cb9ce-109">应为： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb9ce-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cb9ce-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="cb9ce-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb9ce-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb9ce-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cb9ce-112">注解</span><span class="sxs-lookup"><span data-stu-id="cb9ce-112">Remarks</span></span>

<span data-ttu-id="cb9ce-113">这等效于 <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> 带有硬编码容差 $10 ^ {-10} $ 的。</span><span class="sxs-lookup"><span data-stu-id="cb9ce-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>