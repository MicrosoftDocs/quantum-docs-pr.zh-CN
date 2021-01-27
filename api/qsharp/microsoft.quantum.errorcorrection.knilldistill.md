---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853105"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="f2df5-102">KnillDistill 操作</span><span class="sxs-lookup"><span data-stu-id="f2df5-102">KnillDistill operation</span></span>

<span data-ttu-id="f2df5-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f2df5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f2df5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2df5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2df5-105">实现 Knill 幻状态升华算法。</span><span class="sxs-lookup"><span data-stu-id="f2df5-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="f2df5-106">说明</span><span class="sxs-lookup"><span data-stu-id="f2df5-106">Description</span></span>

<span data-ttu-id="f2df5-107">给定15个近似状态 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align} 的 {8} 副本 {1} ，$ $ 会生成一个较高质量的副本。</span><span class="sxs-lookup"><span data-stu-id="f2df5-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="f2df5-108">输入</span><span class="sxs-lookup"><span data-stu-id="f2df5-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="f2df5-109">roughMagic： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f2df5-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f2df5-110">包含神奇状态近似副本的十五个 qubits 寄存器。</span><span class="sxs-lookup"><span data-stu-id="f2df5-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="f2df5-111">此升华过程的以下应用程序 `roughMagic[0]` 将包含一个较高质量的副本，并且寄存器的其余部分将重置为 $ \ket{00\cdots 0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="f2df5-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f2df5-112">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="f2df5-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f2df5-113">如果为 `true` ，则过程成功并且应接受更高质量的副本。</span><span class="sxs-lookup"><span data-stu-id="f2df5-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="f2df5-114">如果 `false` 为，则过程失败，并且应将寄存器的状态视为未定义。</span><span class="sxs-lookup"><span data-stu-id="f2df5-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2df5-115">备注</span><span class="sxs-lookup"><span data-stu-id="f2df5-115">Remarks</span></span>

<span data-ttu-id="f2df5-116">我们采用 Knill 的算法。</span><span class="sxs-lookup"><span data-stu-id="f2df5-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="f2df5-117">但当前的实现远不是最佳的，因为它使用过多的 qubits。</span><span class="sxs-lookup"><span data-stu-id="f2df5-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="f2df5-118">此例程中注入幻状态，在这种情况下，有更好的协议。</span><span class="sxs-lookup"><span data-stu-id="f2df5-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="f2df5-119">参考</span><span class="sxs-lookup"><span data-stu-id="f2df5-119">References</span></span>

- [<span data-ttu-id="f2df5-120">Knill</span><span class="sxs-lookup"><span data-stu-id="f2df5-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)