---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695498"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="4ae09-102">KnillDistill 操作</span><span class="sxs-lookup"><span data-stu-id="4ae09-102">KnillDistill operation</span></span>

<span data-ttu-id="4ae09-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4ae09-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4ae09-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ae09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ae09-105">实现 Knill 幻状态升华算法。</span><span class="sxs-lookup"><span data-stu-id="4ae09-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="4ae09-106">说明</span><span class="sxs-lookup"><span data-stu-id="4ae09-106">Description</span></span>

<span data-ttu-id="4ae09-107">给定15个近似状态 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align} 的 {8} 副本 {1} ，$ $ 会生成一个较高质量的副本。</span><span class="sxs-lookup"><span data-stu-id="4ae09-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="4ae09-108">输入</span><span class="sxs-lookup"><span data-stu-id="4ae09-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="4ae09-109">roughMagic： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4ae09-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4ae09-110">包含神奇状态近似副本的十五个 qubits 寄存器。</span><span class="sxs-lookup"><span data-stu-id="4ae09-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="4ae09-111">此升华过程的以下应用程序 `roughMagic[0]` 将包含一个较高质量的副本，并且寄存器的其余部分将重置为 $ \ket{00\cdots 0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="4ae09-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4ae09-112">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="4ae09-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4ae09-113">如果为 `true` ，则过程成功并且应接受更高质量的副本。</span><span class="sxs-lookup"><span data-stu-id="4ae09-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="4ae09-114">如果 `false` 为，则过程失败，并且应将寄存器的状态视为未定义。</span><span class="sxs-lookup"><span data-stu-id="4ae09-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ae09-115">注解</span><span class="sxs-lookup"><span data-stu-id="4ae09-115">Remarks</span></span>

<span data-ttu-id="4ae09-116">我们采用 Knill 的算法。</span><span class="sxs-lookup"><span data-stu-id="4ae09-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="4ae09-117">但当前的实现远不是最佳的，因为它使用过多的 qubits。</span><span class="sxs-lookup"><span data-stu-id="4ae09-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="4ae09-118">此例程中注入幻状态，在这种情况下，有更好的协议。</span><span class="sxs-lookup"><span data-stu-id="4ae09-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="4ae09-119">参考</span><span class="sxs-lookup"><span data-stu-id="4ae09-119">References</span></span>

- [<span data-ttu-id="4ae09-120">Knill</span><span class="sxs-lookup"><span data-stu-id="4ae09-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)