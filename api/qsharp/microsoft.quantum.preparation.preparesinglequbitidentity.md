---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193618"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="da616-102">PrepareSingleQubitIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="da616-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="da616-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="da616-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="da616-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da616-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da616-105">准备处于最大化混合状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="da616-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="da616-106">它通过应用 depolarizing 通道 $ $ \begin{align} \Omega ( \rho) \mathrel{，在 $ \boldone/$2 状态中准备给定的 qubit： =} \frac {1} {4} \ sum_ {\mu \in \{ 0，1，2，3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}，\end{align} $ $，其中 $ \sigma \_ i $ 是 $i $ th Pauli 运算符，其中 $ \rho $ 是表示混合状态的密度运算符。</span><span class="sxs-lookup"><span data-stu-id="da616-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="da616-107">输入</span><span class="sxs-lookup"><span data-stu-id="da616-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="da616-108">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da616-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="da616-109">其状态为 depolarized 的 qubit。</span><span class="sxs-lookup"><span data-stu-id="da616-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da616-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da616-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="da616-111">备注</span><span class="sxs-lookup"><span data-stu-id="da616-111">Remarks</span></span>

<span data-ttu-id="da616-112">混合状态 $ \boldone/$2 描述将此操作应用于状态的结果。隐式描述此操作中随机选择的预期值。</span><span class="sxs-lookup"><span data-stu-id="da616-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="da616-113">因此，对于任何单个应用程序，此操作都会将纯状态映射到纯状态，但它的行为如预期所述。</span><span class="sxs-lookup"><span data-stu-id="da616-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="da616-114">具体而言，可以在进程 tomography 中使用此操作来度量通道的 *非 unital* 组件。</span><span class="sxs-lookup"><span data-stu-id="da616-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>