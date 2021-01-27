---
uid: Microsoft.Quantum.Intrinsic.M
title: M 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818878"
---
# <a name="m-operation"></a><span data-ttu-id="c23a1-102">M 操作</span><span class="sxs-lookup"><span data-stu-id="c23a1-102">M operation</span></span>

<span data-ttu-id="c23a1-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="c23a1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="c23a1-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c23a1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c23a1-105">对 Pauli $Z $ basis 中的单个 qubit 进行度量。</span><span class="sxs-lookup"><span data-stu-id="c23a1-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="c23a1-106">输出结果由分发 \begin{align} \Pr ( \texttt{Zero} 提供\ket{\psi} ) = \braket{\psi | 0} \braket{0 | \psi}。</span><span class="sxs-lookup"><span data-stu-id="c23a1-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="c23a1-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c23a1-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="c23a1-108">输入</span><span class="sxs-lookup"><span data-stu-id="c23a1-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="c23a1-109">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c23a1-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c23a1-110">要测量的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="c23a1-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c23a1-111">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="c23a1-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c23a1-112">`Zero` 如果观察到 $ + $1 eigenvalue，并 `One` 观察到 $-$1 eigenvalue，则为。</span><span class="sxs-lookup"><span data-stu-id="c23a1-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="c23a1-113">备注</span><span class="sxs-lookup"><span data-stu-id="c23a1-113">Remarks</span></span>

<span data-ttu-id="c23a1-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="c23a1-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```