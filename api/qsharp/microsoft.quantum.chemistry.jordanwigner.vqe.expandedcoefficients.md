---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214375"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="9c3f9-102">ExpandedCoefficients 函数</span><span class="sxs-lookup"><span data-stu-id="9c3f9-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="9c3f9-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="9c3f9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="9c3f9-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9c3f9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9c3f9-105">展开 Jordan-Wigner 系数的精简表示形式，以便在这些条款和 Pauli 条款之间获取一对一的映射。</span><span class="sxs-lookup"><span data-stu-id="9c3f9-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="9c3f9-106">输入</span><span class="sxs-lookup"><span data-stu-id="9c3f9-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="9c3f9-107">coeff： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9c3f9-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9c3f9-108">作为从 Jordan-Wigner Hamiltonian 数据结构读取的系数的数组。</span><span class="sxs-lookup"><span data-stu-id="9c3f9-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="9c3f9-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c3f9-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c3f9-110">Jordan-Wigner 术语的类型。</span><span class="sxs-lookup"><span data-stu-id="9c3f9-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="9c3f9-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9c3f9-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9c3f9-112">扩展的系数数组，每个 Pauli 项一个。</span><span class="sxs-lookup"><span data-stu-id="9c3f9-112">Expanded arrays of coefficients, one per Pauli term.</span></span>