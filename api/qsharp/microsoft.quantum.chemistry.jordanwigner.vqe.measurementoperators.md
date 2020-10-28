---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695698"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="eb2d6-102">MeasurementOperators 函数</span><span class="sxs-lookup"><span data-stu-id="eb2d6-102">MeasurementOperators function</span></span>

<span data-ttu-id="eb2d6-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="eb2d6-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="eb2d6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb2d6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb2d6-105">计算计算 Jordan-Wigner 术语的预期所需的所有度量运算符。</span><span class="sxs-lookup"><span data-stu-id="eb2d6-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="eb2d6-106">输入</span><span class="sxs-lookup"><span data-stu-id="eb2d6-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="eb2d6-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb2d6-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb2d6-108">模拟分子系统所需的 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="eb2d6-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="eb2d6-109">索引： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="eb2d6-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="eb2d6-110">一个数组，该数组包含将每个 Pauli 运算符应用到的 qubit 的索引。</span><span class="sxs-lookup"><span data-stu-id="eb2d6-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="eb2d6-111">termType： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb2d6-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb2d6-112">Jordan-Wigner 术语的类型。</span><span class="sxs-lookup"><span data-stu-id="eb2d6-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="eb2d6-113">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="eb2d6-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="eb2d6-114">度量运算符数组 (每个都是 Pauli) 的数组。</span><span class="sxs-lookup"><span data-stu-id="eb2d6-114">An array of measurement operators (each being an array of Pauli).</span></span>