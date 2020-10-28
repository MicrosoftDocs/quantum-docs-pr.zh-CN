---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695703"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="3ce0c-102">ExpandedCoefficients 函数</span><span class="sxs-lookup"><span data-stu-id="3ce0c-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="3ce0c-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="3ce0c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="3ce0c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ce0c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ce0c-105">展开 Jordan-Wigner 系数的精简表示形式，以便在这些条款和 Pauli 条款之间获取一对一的映射。</span><span class="sxs-lookup"><span data-stu-id="3ce0c-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="3ce0c-106">输入</span><span class="sxs-lookup"><span data-stu-id="3ce0c-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="3ce0c-107">coeff： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3ce0c-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3ce0c-108">作为从 Jordan-Wigner Hamiltonian 数据结构读取的系数的数组。</span><span class="sxs-lookup"><span data-stu-id="3ce0c-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="3ce0c-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ce0c-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ce0c-110">Jordan-Wigner 术语的类型。</span><span class="sxs-lookup"><span data-stu-id="3ce0c-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="3ce0c-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3ce0c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3ce0c-112">扩展的系数数组，每个 Pauli 项一个。</span><span class="sxs-lookup"><span data-stu-id="3ce0c-112">Expanded arrays of coefficients, one per Pauli term.</span></span>