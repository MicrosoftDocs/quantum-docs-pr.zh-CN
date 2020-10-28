---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695876"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="8d166-102">SingleQubitProcessTomographyMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="8d166-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="8d166-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="8d166-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="8d166-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d166-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d166-105">根据感兴趣的特定通道，在 Pauli 基础上执行 qubit 进程 tomography 度量。</span><span class="sxs-lookup"><span data-stu-id="8d166-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="8d166-106">输入</span><span class="sxs-lookup"><span data-stu-id="8d166-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="8d166-107">准备： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="8d166-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="8d166-108">Pauli basis 元素 $P $，其中 qubit 准备就绪。</span><span class="sxs-lookup"><span data-stu-id="8d166-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="8d166-109">度量： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="8d166-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="8d166-110">Pauli 基础元素 $Q $，其中 qubit 将在其中进行度量。</span><span class="sxs-lookup"><span data-stu-id="8d166-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="8d166-111">频道： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d166-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8d166-112">使用进程 tomography 估计其行为的单个 qubit 通道 $ \Lambda $。</span><span class="sxs-lookup"><span data-stu-id="8d166-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8d166-113">输出： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="8d166-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="8d166-114">概率为 `Zero` $ $ \Begin{align} \Pr ( \texttt{zero} | \Lambda; 的结果P，Q) = \operatorname{Tr}\left ( \frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right) 。</span><span class="sxs-lookup"><span data-stu-id="8d166-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="8d166-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8d166-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="8d166-116">注解</span><span class="sxs-lookup"><span data-stu-id="8d166-116">Remarks</span></span>

<span data-ttu-id="8d166-117">此操作返回的结果的分布是 qubit 状态 tomography 的一种特殊情况。</span><span class="sxs-lookup"><span data-stu-id="8d166-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="8d166-118">让 $ \rho = J ( \Lambda) /$2 作为 $ \Lambda $ 的 Choi – Jamiłkowski 状态。</span><span class="sxs-lookup"><span data-stu-id="8d166-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="8d166-119">然后，上面的分发与 $ $ \begin{align} \Pr ( \texttt{Zero} |rhoM) = \operatorname{Tr} (M \rho) ，\end{align} $ $，其中 $M = 2 ( \boldone + P) ^ \mathrm{T}/2 \cdot ( \boldone + Q) /$2 是对应于 $P $ 和 $Q $ 的有效度量值。</span><span class="sxs-lookup"><span data-stu-id="8d166-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>