---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: OptimizedTrotterStepOracle 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f78d80f7ab71f4fc759d8045c9a134d7178aaa15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695280"
---
# <a name="optimizedtrottersteporacle-function"></a><span data-ttu-id="1b41e-102">OptimizedTrotterStepOracle 函数</span><span class="sxs-lookup"><span data-stu-id="1b41e-102">OptimizedTrotterStepOracle function</span></span>

<span data-ttu-id="1b41e-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1b41e-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="1b41e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b41e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b41e-105">返回优化的 Trotter 步骤操作和运行它所需的参数。</span><span class="sxs-lookup"><span data-stu-id="1b41e-105">Returns optimized Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="1b41e-106">输入</span><span class="sxs-lookup"><span data-stu-id="1b41e-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="1b41e-107">qSharpData： [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="1b41e-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="1b41e-108">格式描述的 Hamiltonian `JordanWignerEncodingData` 。</span><span class="sxs-lookup"><span data-stu-id="1b41e-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="1b41e-109">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1b41e-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1b41e-110">Trotter 集成器的步长大小。</span><span class="sxs-lookup"><span data-stu-id="1b41e-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="1b41e-111">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b41e-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b41e-112">Trotter 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="1b41e-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="1b41e-113">Output： ([Int](xref:microsoft.quantum.lang-ref.int)、 ([Double](xref:microsoft.quantum.lang-ref.double)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl) # A3</span><span class="sxs-lookup"><span data-stu-id="1b41e-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="1b41e-114">元组，其中： `Int` 是已分配的 qubits 的数目， `Double` 是 `1.0/trotterStepSize` ，操作是 Trotter 步骤。</span><span class="sxs-lookup"><span data-stu-id="1b41e-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>