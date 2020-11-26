---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: e56e84effa001f104bbd5e28e7181dbd39a4cf5e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201285"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="65a4a-102">ApplyBitFlipEncoder 操作</span><span class="sxs-lookup"><span data-stu-id="65a4a-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="65a4a-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="65a4a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="65a4a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65a4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65a4a-105">用于实现位翻转编码器和解码器的专用操作。</span><span class="sxs-lookup"><span data-stu-id="65a4a-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="65a4a-106">请注意，此编码器可以利用就地一致恢复，在这种情况下，它将 "导致" 的初始状态描述的错误 `auxQubits` 。</span><span class="sxs-lookup"><span data-stu-id="65a4a-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="65a4a-107">具体而言，如果 `auxQubits` 最初处于状态 $ \ket {10} $，这将导致在编码的 qubit 上出现 $X _1 $ 错误。</span><span class="sxs-lookup"><span data-stu-id="65a4a-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="65a4a-108">输入</span><span class="sxs-lookup"><span data-stu-id="65a4a-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="65a4a-109">coherentRecovery： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="65a4a-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="65a4a-110">数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="65a4a-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="65a4a-111">草稿： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="65a4a-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="65a4a-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65a4a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="65a4a-113">参考</span><span class="sxs-lookup"><span data-stu-id="65a4a-113">References</span></span>

- <span data-ttu-id="65a4a-114">doi>10.1145： 10.1103/PhysRevA 85.044302</span><span class="sxs-lookup"><span data-stu-id="65a4a-114">doi:10.1103/PhysRevA.85.044302</span></span>