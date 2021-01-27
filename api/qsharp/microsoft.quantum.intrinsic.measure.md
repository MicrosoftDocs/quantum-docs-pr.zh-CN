---
uid: Microsoft.Quantum.Intrinsic.Measure
title: 度量运算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818769"
---
# <a name="measure-operation"></a><span data-ttu-id="ca739-102">度量运算</span><span class="sxs-lookup"><span data-stu-id="ca739-102">Measure operation</span></span>

<span data-ttu-id="ca739-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ca739-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ca739-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ca739-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ca739-105">对指定的 Pauli 中的一个或多个 qubits 执行联合度量。</span><span class="sxs-lookup"><span data-stu-id="ca739-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="ca739-106">输出结果由分发提供： \begin{align} \Pr ( \texttt{Zero} |\ket{\psi} ) = \frac12 \braket{\psi \mid | \left ( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}，\end{align} 其中 $P _i $ 是的 $i $ th 元素 `bases` ，其中 $N = \texttt{Length} ( \texttt{bases} ) $。</span><span class="sxs-lookup"><span data-stu-id="ca739-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="ca739-107">也就是说，度量值返回 $d $，以使 `Result` 观察到的度量值的 eigenvalue 为 $ (-1) ^ d $。</span><span class="sxs-lookup"><span data-stu-id="ca739-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="ca739-108">输入</span><span class="sxs-lookup"><span data-stu-id="ca739-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="ca739-109">基： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ca739-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ca739-110">Qubit Pauli 值的数组，用于指示每个 qubit 上的 tensor 产品因素。</span><span class="sxs-lookup"><span data-stu-id="ca739-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ca739-111">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ca739-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ca739-112">注册要测量的 qubits。</span><span class="sxs-lookup"><span data-stu-id="ca739-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ca739-113">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="ca739-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ca739-114">`Zero` 如果观察到 $ + $1 eigenvalue，并 `One` 观察到 $-$1 eigenvalue，则为。</span><span class="sxs-lookup"><span data-stu-id="ca739-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca739-115">备注</span><span class="sxs-lookup"><span data-stu-id="ca739-115">Remarks</span></span>

<span data-ttu-id="ca739-116">如果基础数组和 qubit 数组的长度不同，则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="ca739-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>