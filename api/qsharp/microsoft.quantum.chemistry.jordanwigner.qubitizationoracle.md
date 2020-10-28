---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: QubitizationOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: 326bebfc1cfd839082732898167c20ecf105a266
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695717"
---
# <a name="qubitizationoracle-function"></a><span data-ttu-id="4e8ec-102">QubitizationOracle 函数</span><span class="sxs-lookup"><span data-stu-id="4e8ec-102">QubitizationOracle function</span></span>

<span data-ttu-id="4e8ec-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4e8ec-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4e8ec-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e8ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e8ec-105">返回 Qubitization 操作和运行该操作所需的参数。</span><span class="sxs-lookup"><span data-stu-id="4e8ec-105">Returns Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="4e8ec-106">输入</span><span class="sxs-lookup"><span data-stu-id="4e8ec-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="4e8ec-107">qSharpData： [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="4e8ec-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="4e8ec-108">格式描述的 Hamiltonian `JordanWignerEncodingData` 。</span><span class="sxs-lookup"><span data-stu-id="4e8ec-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="4e8ec-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)、 ([Double](xref:microsoft.quantum.lang-ref.double)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl) # A3</span><span class="sxs-lookup"><span data-stu-id="4e8ec-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="4e8ec-110">元组，其中： `Int` 是已分配的 qubits 数， `Double` 是 Hamiltonian 系数的一种标准，操作是 Qubitization 创建的量程审核。</span><span class="sxs-lookup"><span data-stu-id="4e8ec-110">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>