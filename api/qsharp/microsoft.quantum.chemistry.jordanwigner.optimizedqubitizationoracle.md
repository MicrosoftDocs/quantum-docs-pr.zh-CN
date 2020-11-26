---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle
title: OptimizedQubitizationOracle 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedQubitizationOracle
qsharp.summary: Returns T-count optimized Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: d20fe3bfe362a94c23ec266efaebfda73d7baf82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224779"
---
# <a name="optimizedqubitizationoracle-function"></a><span data-ttu-id="d63e1-102">OptimizedQubitizationOracle 函数</span><span class="sxs-lookup"><span data-stu-id="d63e1-102">OptimizedQubitizationOracle function</span></span>

<span data-ttu-id="d63e1-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d63e1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d63e1-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d63e1-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="d63e1-105">返回 T-sql 优化 Qubitization 操作和运行该操作所需的参数。</span><span class="sxs-lookup"><span data-stu-id="d63e1-105">Returns T-count optimized Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function OptimizedQubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, targetError : Double) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="d63e1-106">输入</span><span class="sxs-lookup"><span data-stu-id="d63e1-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="d63e1-107">qSharpData： [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="d63e1-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="d63e1-108">格式描述的 Hamiltonian `JordanWignerEncodingData` 。</span><span class="sxs-lookup"><span data-stu-id="d63e1-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="targeterror--double"></a><span data-ttu-id="d63e1-109">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d63e1-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d63e1-110">辅助状态准备步骤出错。</span><span class="sxs-lookup"><span data-stu-id="d63e1-110">Error of auxillary state preparation step.</span></span>



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a><span data-ttu-id="d63e1-111">Output： ([Int](xref:microsoft.quantum.lang-ref.int)、 ([Double](xref:microsoft.quantum.lang-ref.double)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl) # A3</span><span class="sxs-lookup"><span data-stu-id="d63e1-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl))</span></span>

<span data-ttu-id="d63e1-112">元组，其中： `Int` 是已分配的 qubits 数， `Double` 是 Hamiltonian 系数的一种标准，操作是 Qubitization 创建的量程审核。</span><span class="sxs-lookup"><span data-stu-id="d63e1-112">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>