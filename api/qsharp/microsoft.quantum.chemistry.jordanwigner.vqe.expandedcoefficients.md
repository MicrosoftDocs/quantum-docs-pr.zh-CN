---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835620"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="8d0da-102">ExpandedCoefficients 函数</span><span class="sxs-lookup"><span data-stu-id="8d0da-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="8d0da-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="8d0da-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="8d0da-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="8d0da-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="8d0da-105">展开 Jordan-Wigner 系数的精简表示形式，以便在这些条款和 Pauli 条款之间获取一对一的映射。</span><span class="sxs-lookup"><span data-stu-id="8d0da-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="8d0da-106">输入</span><span class="sxs-lookup"><span data-stu-id="8d0da-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="8d0da-107">coeff： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8d0da-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8d0da-108">作为从 Jordan-Wigner Hamiltonian 数据结构读取的系数的数组。</span><span class="sxs-lookup"><span data-stu-id="8d0da-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="8d0da-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d0da-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d0da-110">Jordan-Wigner 术语的类型。</span><span class="sxs-lookup"><span data-stu-id="8d0da-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="8d0da-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8d0da-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8d0da-112">扩展的系数数组，每个 Pauli 项一个。</span><span class="sxs-lookup"><span data-stu-id="8d0da-112">Expanded arrays of coefficients, one per Pauli term.</span></span>