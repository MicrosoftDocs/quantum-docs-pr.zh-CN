---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851055"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="10d6d-102">QuantumWalkByQubitization 函数</span><span class="sxs-lookup"><span data-stu-id="10d6d-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="10d6d-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="10d6d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="10d6d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10d6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10d6d-105">将块编码反射转换为量程审核。</span><span class="sxs-lookup"><span data-stu-id="10d6d-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="10d6d-106">说明</span><span class="sxs-lookup"><span data-stu-id="10d6d-106">Description</span></span>

<span data-ttu-id="10d6d-107">给定一个 `BlockEncodingReflection` 由单一 $U $ 表示的，用来对某个运算符 $H $ 相关的运算符进行编码，并将其转换为量程审核 $W $，其中包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的范围。</span><span class="sxs-lookup"><span data-stu-id="10d6d-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="10d6d-108">输入</span><span class="sxs-lookup"><span data-stu-id="10d6d-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="10d6d-109">blockEncoding： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="10d6d-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="10d6d-110">`BlockEncodingReflection`要转换为量程审核的单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="10d6d-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="10d6d-111">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="10d6d-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="10d6d-112">量程审核 $W $ 联合在寄存器上， `a` 并对 `s` $H $ 进行阻止编码，并包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的范围。</span><span class="sxs-lookup"><span data-stu-id="10d6d-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="10d6d-113">参考</span><span class="sxs-lookup"><span data-stu-id="10d6d-113">References</span></span>

- <span data-ttu-id="10d6d-114">Hamiltonian 模拟 by Qubitization Guang 脱离 Hao Low、Isaac 语 https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="10d6d-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="10d6d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10d6d-115">See Also</span></span>

- [<span data-ttu-id="10d6d-116">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="10d6d-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="10d6d-117">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="10d6d-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)