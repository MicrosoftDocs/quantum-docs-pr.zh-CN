---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerOptimizedBlockEncodingStatePrep
title: _JordanWignerOptimizedBlockEncodingStatePrep 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerOptimizedBlockEncodingStatePrep
qsharp.summary: ''
ms.openlocfilehash: 5161c68552b3748534e81acc2eff558d57cbec8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695819"
---
# <a name="_jordanwigneroptimizedblockencodingstateprep-operation"></a><span data-ttu-id="96e45-102">_JordanWignerOptimizedBlockEncodingStatePrep 操作</span><span class="sxs-lookup"><span data-stu-id="96e45-102">_JordanWignerOptimizedBlockEncodingStatePrep operation</span></span>

<span data-ttu-id="96e45-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="96e45-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="96e45-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96e45-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation _JordanWignerOptimizedBlockEncodingStatePrep (targetError : Double, optimizedBEGeneratorSystem : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem, qROMIdxRegister : Microsoft.Quantum.Arithmetic.LittleEndian, qROMGarbage : Qubit[], signQubit : Qubit, selectZControlRegisters : Qubit[], OptimizedBEControlRegisters : Qubit[], pauliBases : Qubit[], pauliBasesIdx : Microsoft.Quantum.Arithmetic.LittleEndian, indexRegisters : Microsoft.Quantum.Arithmetic.LittleEndian[]) : Unit
```


## <a name="input"></a><span data-ttu-id="96e45-105">输入</span><span class="sxs-lookup"><span data-stu-id="96e45-105">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="96e45-106">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96e45-106">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="optimizedbegeneratorsystem--optimizedbegeneratorsystem"></a><span data-ttu-id="96e45-107">optimizedBEGeneratorSystem： [optimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="96e45-107">optimizedBEGeneratorSystem : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>




### <a name="qromidxregister--littleendian"></a><span data-ttu-id="96e45-108">qROMIdxRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="96e45-108">qROMIdxRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="qromgarbage--qubit"></a><span data-ttu-id="96e45-109">qROMGarbage： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="96e45-109">qROMGarbage : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="signqubit--qubit"></a><span data-ttu-id="96e45-110">signQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="96e45-110">signQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="selectzcontrolregisters--qubit"></a><span data-ttu-id="96e45-111">selectZControlRegisters： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="96e45-111">selectZControlRegisters : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="optimizedbecontrolregisters--qubit"></a><span data-ttu-id="96e45-112">OptimizedBEControlRegisters： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="96e45-112">OptimizedBEControlRegisters : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="paulibases--qubit"></a><span data-ttu-id="96e45-113">pauliBases： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="96e45-113">pauliBases : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="paulibasesidx--littleendian"></a><span data-ttu-id="96e45-114">pauliBasesIdx： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="96e45-114">pauliBasesIdx : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="indexregisters--littleendian"></a><span data-ttu-id="96e45-115">indexRegisters： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]</span><span class="sxs-lookup"><span data-stu-id="96e45-115">indexRegisters : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="96e45-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96e45-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

