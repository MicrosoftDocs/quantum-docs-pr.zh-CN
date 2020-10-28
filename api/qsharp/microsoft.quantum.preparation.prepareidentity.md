---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700972"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="15f5a-102">PrepareIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="15f5a-102">PrepareIdentity operation</span></span>

<span data-ttu-id="15f5a-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="15f5a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="15f5a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15f5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15f5a-105">在给定寄存器的情况下，准备在最大化 mixed 状态下进行注册。</span><span class="sxs-lookup"><span data-stu-id="15f5a-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="15f5a-106">在 $ \boldone/2 ^ N $ 状态下注册注册，方法是将完整的 depolarizing 通道应用于每个 qubit，其中 $N $ 是寄存器的长度。</span><span class="sxs-lookup"><span data-stu-id="15f5a-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="15f5a-107">输入</span><span class="sxs-lookup"><span data-stu-id="15f5a-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="15f5a-108">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="15f5a-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="15f5a-109">其状态为 depolarized 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="15f5a-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15f5a-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15f5a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="15f5a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15f5a-111">See Also</span></span>

- [<span data-ttu-id="15f5a-112">PrepareSingleQubitIdentity。</span><span class="sxs-lookup"><span data-stu-id="15f5a-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)