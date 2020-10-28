---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: TrotterStepOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f7659616ea39d781137c26965cbf2005c5e634b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695711"
---
# <a name="trottersteporacle-function"></a><span data-ttu-id="0bed3-102">TrotterStepOracle 函数</span><span class="sxs-lookup"><span data-stu-id="0bed3-102">TrotterStepOracle function</span></span>

<span data-ttu-id="0bed3-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="0bed3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="0bed3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bed3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bed3-105">返回 Trotter 步骤操作和运行该操作所需的参数。</span><span class="sxs-lookup"><span data-stu-id="0bed3-105">Returns Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function TrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="0bed3-106">输入</span><span class="sxs-lookup"><span data-stu-id="0bed3-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="0bed3-107">qSharpData： [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="0bed3-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="0bed3-108">格式描述的 Hamiltonian `JordanWignerEncodingData` 。</span><span class="sxs-lookup"><span data-stu-id="0bed3-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="0bed3-109">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0bed3-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0bed3-110">Trotter 集成器的步长大小。</span><span class="sxs-lookup"><span data-stu-id="0bed3-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="0bed3-111">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0bed3-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0bed3-112">Trotter 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="0bed3-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="0bed3-113">Output： ([Int](xref:microsoft.quantum.lang-ref.int)、 ([Double](xref:microsoft.quantum.lang-ref.double)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl) # A3</span><span class="sxs-lookup"><span data-stu-id="0bed3-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="0bed3-114">元组，其中： `Int` 是已分配的 qubits 的数目， `Double` 是 `1.0/trotterStepSize` ，操作是 Trotter 步骤。</span><span class="sxs-lookup"><span data-stu-id="0bed3-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>