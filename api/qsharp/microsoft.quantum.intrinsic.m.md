---
uid: Microsoft.Quantum.Intrinsic.M
title: M 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699805"
---
# <a name="m-operation"></a><span data-ttu-id="832fe-102">M 操作</span><span class="sxs-lookup"><span data-stu-id="832fe-102">M operation</span></span>

<span data-ttu-id="832fe-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="832fe-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="832fe-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="832fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="832fe-105">对 Pauli $Z $ basis 中的单个 qubit 进行度量。</span><span class="sxs-lookup"><span data-stu-id="832fe-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="832fe-106">输出结果由分发 \begin{align} \Pr ( \texttt{Zero} 提供\ket{\psi} ) = \braket{\psi | 0} \braket{0 | \psi}。</span><span class="sxs-lookup"><span data-stu-id="832fe-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="832fe-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="832fe-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="832fe-108">输入</span><span class="sxs-lookup"><span data-stu-id="832fe-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="832fe-109">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="832fe-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="832fe-110">要测量的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="832fe-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="832fe-111">输出： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="832fe-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="832fe-112">`Zero` 如果观察到 $ + $1 eigenvalue，并 `One` 观察到 $-$1 eigenvalue，则为。</span><span class="sxs-lookup"><span data-stu-id="832fe-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="832fe-113">注解</span><span class="sxs-lookup"><span data-stu-id="832fe-113">Remarks</span></span>

<span data-ttu-id="832fe-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="832fe-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```