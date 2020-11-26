---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210431"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="902a9-102">PrepareIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="902a9-102">PrepareIdentity operation</span></span>

<span data-ttu-id="902a9-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="902a9-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="902a9-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="902a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="902a9-105">在给定寄存器的情况下，准备在最大化 mixed 状态下进行注册。</span><span class="sxs-lookup"><span data-stu-id="902a9-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="902a9-106">在 $ \boldone/2 ^ N $ 状态下注册注册，方法是将完整的 depolarizing 通道应用于每个 qubit，其中 $N $ 是寄存器的长度。</span><span class="sxs-lookup"><span data-stu-id="902a9-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="902a9-107">输入</span><span class="sxs-lookup"><span data-stu-id="902a9-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="902a9-108">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="902a9-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="902a9-109">其状态为 depolarized 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="902a9-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="902a9-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="902a9-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="902a9-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="902a9-111">See Also</span></span>

- [<span data-ttu-id="902a9-112">PrepareSingleQubitIdentity。</span><span class="sxs-lookup"><span data-stu-id="902a9-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)