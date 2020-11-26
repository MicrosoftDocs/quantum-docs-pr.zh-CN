---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 97a410133e80cc5bffc810e9d6455baaee32364b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207694"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="dc2a6-102">ApproximateQFT 操作</span><span class="sxs-lookup"><span data-stu-id="dc2a6-102">ApproximateQFT operation</span></span>

<span data-ttu-id="dc2a6-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc2a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc2a6-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc2a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc2a6-105">将大致的量程傅立叶转换 (AQFT) 应用到一个量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="dc2a6-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dc2a6-106">输入</span><span class="sxs-lookup"><span data-stu-id="dc2a6-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dc2a6-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc2a6-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc2a6-108">确定 QFT 线路中发生的受控 Z 旋转在哪个级别上被修剪的近似值参数。</span><span class="sxs-lookup"><span data-stu-id="dc2a6-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="dc2a6-109">近似值参数 a 确定 Z 旋转的修剪级别，即∈ {0 ... n} 和所有 Z 旋转 2π/2k，其中 k>从 QFT 线路中删除。</span><span class="sxs-lookup"><span data-stu-id="dc2a6-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="dc2a6-110">知道，对于 k >= log ₂ (n) + log ₂ (1/ε) + 3 1 可以绑定 | |QFT-AQFT | |<ε。</span><span class="sxs-lookup"><span data-stu-id="dc2a6-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="dc2a6-111">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="dc2a6-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="dc2a6-112">应用大致量程傅立叶转换的 n qubits 的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="dc2a6-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc2a6-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc2a6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dc2a6-114">备注</span><span class="sxs-lookup"><span data-stu-id="dc2a6-114">Remarks</span></span>

<span data-ttu-id="dc2a6-115">AQFT 需要 2π/2k 和 Hadamard 入口的 Z 旋转入口。</span><span class="sxs-lookup"><span data-stu-id="dc2a6-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="dc2a6-116">输入和输出假定为以大字节序编码进行编码。</span><span class="sxs-lookup"><span data-stu-id="dc2a6-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="dc2a6-117">参考</span><span class="sxs-lookup"><span data-stu-id="dc2a6-117">References</span></span>

- [<span data-ttu-id="dc2a6-118">*Roetteler，Beth*，Appl.exe，Commun。计算机.19 (3) ： 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="dc2a6-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="dc2a6-119">*D. Coppersmith* arXiv： quant/0201067v1</span><span class="sxs-lookup"><span data-stu-id="dc2a6-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)