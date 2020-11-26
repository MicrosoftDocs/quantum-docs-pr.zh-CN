---
uid: Microsoft.Quantum.Preparation.PrepareQuantumROMState
title: PrepareQuantumROMState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQuantumROMState
qsharp.summary: ''
ms.openlocfilehash: 41b3a041ad3cef466e780fa9e88ab8ab72269e66
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193499"
---
# <a name="preparequantumromstate-operation"></a><span data-ttu-id="1d181-102">PrepareQuantumROMState 操作</span><span class="sxs-lookup"><span data-stu-id="1d181-102">PrepareQuantumROMState operation</span></span>

<span data-ttu-id="1d181-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="1d181-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="1d181-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d181-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation PrepareQuantumROMState (nBitsPrecision : Int, nCoeffs : Int, nBitsIndices : Int, keepCoeff : Int[], altIndex : Int[], data : Bool[][], indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, dataQubits : Qubit[], garbageRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1d181-105">输入</span><span class="sxs-lookup"><span data-stu-id="1d181-105">Input</span></span>

### <a name="nbitsprecision--int"></a><span data-ttu-id="1d181-106">nBitsPrecision： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d181-106">nBitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="ncoeffs--int"></a><span data-ttu-id="1d181-107">nCoeffs： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d181-107">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nbitsindices--int"></a><span data-ttu-id="1d181-108">nBitsIndices： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d181-108">nBitsIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="keepcoeff--int"></a><span data-ttu-id="1d181-109">keepCoeff： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1d181-109">keepCoeff : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="altindex--int"></a><span data-ttu-id="1d181-110">altIndex： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1d181-110">altIndex : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="data--bool"></a><span data-ttu-id="1d181-111">数据： [Bool](xref:microsoft.quantum.lang-ref.bool)[] []</span><span class="sxs-lookup"><span data-stu-id="1d181-111">data : [Bool](xref:microsoft.quantum.lang-ref.bool)[][]</span></span>




### <a name="indexregister--littleendian"></a><span data-ttu-id="1d181-112">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d181-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="dataqubits--qubit"></a><span data-ttu-id="1d181-113">dataQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1d181-113">dataQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="garbageregister--qubit"></a><span data-ttu-id="1d181-114">garbageRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1d181-114">garbageRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="1d181-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d181-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

