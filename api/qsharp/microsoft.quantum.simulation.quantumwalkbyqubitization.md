---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701168"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="0ab19-102">QuantumWalkByQubitization 函数</span><span class="sxs-lookup"><span data-stu-id="0ab19-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="0ab19-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0ab19-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0ab19-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0ab19-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0ab19-105">将块编码反射转换为量程审核。</span><span class="sxs-lookup"><span data-stu-id="0ab19-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="0ab19-106">说明</span><span class="sxs-lookup"><span data-stu-id="0ab19-106">Description</span></span>

<span data-ttu-id="0ab19-107">给定一个 `BlockEncodingReflection` 由单一 $U $ 表示的，用来对某个运算符 $H $ 相关的运算符进行编码，并将其转换为量程审核 $W $，其中包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的范围。</span><span class="sxs-lookup"><span data-stu-id="0ab19-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="0ab19-108">输入</span><span class="sxs-lookup"><span data-stu-id="0ab19-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="0ab19-109">blockEncoding： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="0ab19-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="0ab19-110">`BlockEncodingReflection`要转换为量程审核的单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="0ab19-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="0ab19-111">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0ab19-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0ab19-112">量程审核 $W $ 联合在寄存器上， `a` 并对 `s` $H $ 进行阻止编码，并包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的范围。</span><span class="sxs-lookup"><span data-stu-id="0ab19-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="0ab19-113">参考</span><span class="sxs-lookup"><span data-stu-id="0ab19-113">References</span></span>

- <span data-ttu-id="0ab19-114">Hamiltonian 模拟 by Qubitization Guang 脱离 Hao Low、Isaac 语 https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="0ab19-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="0ab19-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ab19-115">See Also</span></span>

- [<span data-ttu-id="0ab19-116">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="0ab19-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="0ab19-117">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="0ab19-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)