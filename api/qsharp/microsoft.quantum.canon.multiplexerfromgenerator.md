---
uid: Microsoft.Quantum.Canon.MultiplexerFromGenerator
title: MultiplexerFromGenerator 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 327d995d3870732887f880778eb289c3aad1f030
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696014"
---
# <a name="multiplexerfromgenerator-function"></a><span data-ttu-id="02887-102">MultiplexerFromGenerator 函数</span><span class="sxs-lookup"><span data-stu-id="02887-102">MultiplexerFromGenerator function</span></span>

<span data-ttu-id="02887-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="02887-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="02887-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02887-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02887-105">返回 $U $ 的乘法控制的单一操作，该操作将应用单一 $V _j $，由 n qubit number state $ \ket{j} $ 控制。</span><span class="sxs-lookup"><span data-stu-id="02887-105">Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="02887-106">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="02887-106">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
function MultiplexerFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="02887-107">输入</span><span class="sxs-lookup"><span data-stu-id="02887-107">Input</span></span>

### <a name="unitarygenerator--intint---qubit--unit-adj--ctl"></a><span data-ttu-id="02887-108">unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="02887-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="02887-109">一个元组，其中第一个元素 `Int` 是 unitaries $N $ 的数量，第二个元素 `(Int -> ('T => () is Adj + Ctl))` 是在 $ [0，N-1] $ 中采用整数 $j $ 并输出单一运算 $V _j $ 的函数。</span><span class="sxs-lookup"><span data-stu-id="02887-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>



## <a name="output--littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="02887-110">Output： ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="02887-110">Output : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="02887-111">按 $U $ 的乘法控制的单一操作，该操作将应用描述的 unitaries `unitaryGenerator` 。</span><span class="sxs-lookup"><span data-stu-id="02887-111">A multiply-controlled unitary operation $U$ that applies unitaries described by `unitaryGenerator`.</span></span>

## <a name="see-also"></a><span data-ttu-id="02887-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02887-112">See Also</span></span>

- [<span data-ttu-id="02887-113">Canon. MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="02887-113">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)