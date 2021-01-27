---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839644"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="51fff-102">SingleQubitProcessTomographyMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="51fff-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="51fff-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="51fff-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="51fff-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51fff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51fff-105">根据感兴趣的特定通道，在 Pauli 基础上执行 qubit 进程 tomography 度量。</span><span class="sxs-lookup"><span data-stu-id="51fff-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="51fff-106">输入</span><span class="sxs-lookup"><span data-stu-id="51fff-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="51fff-107">准备： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="51fff-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="51fff-108">Pauli basis 元素 $P $，其中 qubit 准备就绪。</span><span class="sxs-lookup"><span data-stu-id="51fff-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="51fff-109">度量： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="51fff-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="51fff-110">Pauli 基础元素 $Q $，其中 qubit 将在其中进行度量。</span><span class="sxs-lookup"><span data-stu-id="51fff-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="51fff-111">频道： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51fff-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="51fff-112">使用进程 tomography 估计其行为的单个 qubit 通道 $ \Lambda $。</span><span class="sxs-lookup"><span data-stu-id="51fff-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="51fff-113">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="51fff-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="51fff-114">概率为 `Zero` $ $ \Begin{align} \Pr ( \texttt{zero} | \Lambda; 的结果P，Q) = \operatorname{Tr}\left ( \frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right) 。</span><span class="sxs-lookup"><span data-stu-id="51fff-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="51fff-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="51fff-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="51fff-116">备注</span><span class="sxs-lookup"><span data-stu-id="51fff-116">Remarks</span></span>

<span data-ttu-id="51fff-117">此操作返回的结果的分布是 qubit 状态 tomography 的一种特殊情况。</span><span class="sxs-lookup"><span data-stu-id="51fff-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="51fff-118">让 $ \rho = J ( \Lambda) /$2 作为 $ \Lambda $ 的 Choi – Jamiłkowski 状态。</span><span class="sxs-lookup"><span data-stu-id="51fff-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="51fff-119">然后，上面的分发与 $ $ \begin{align} \Pr ( \texttt{Zero} |rhoM) = \operatorname{Tr} (M \rho) ，\end{align} $ $，其中 $M = 2 ( \boldone + P) ^ \mathrm{T}/2 \cdot ( \boldone + Q) /$2 是对应于 $P $ 和 $Q $ 的有效度量值。</span><span class="sxs-lookup"><span data-stu-id="51fff-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>