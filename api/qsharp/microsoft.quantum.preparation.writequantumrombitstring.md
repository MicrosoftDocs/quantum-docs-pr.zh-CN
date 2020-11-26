---
uid: Microsoft.Quantum.Preparation.WriteQuantumROMBitString
title: WriteQuantumROMBitString 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: WriteQuantumROMBitString
qsharp.summary: ''
ms.openlocfilehash: cee30a37cca418b6d0122416ce122576511cf303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193176"
---
# <a name="writequantumrombitstring-operation"></a><span data-ttu-id="52f3d-102">WriteQuantumROMBitString 操作</span><span class="sxs-lookup"><span data-stu-id="52f3d-102">WriteQuantumROMBitString operation</span></span>

<span data-ttu-id="52f3d-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="52f3d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="52f3d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52f3d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation WriteQuantumROMBitString (idx : Int, keepCoeff : Int[], altIndex : Int[], data : Bool[][], keepCoeffRegister : Microsoft.Quantum.Arithmetic.LittleEndian, altIndexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, dataRegister : Qubit[], altDataRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="52f3d-105">输入</span><span class="sxs-lookup"><span data-stu-id="52f3d-105">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="52f3d-106">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="52f3d-106">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="keepcoeff--int"></a><span data-ttu-id="52f3d-107">keepCoeff： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="52f3d-107">keepCoeff : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="altindex--int"></a><span data-ttu-id="52f3d-108">altIndex： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="52f3d-108">altIndex : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="data--bool"></a><span data-ttu-id="52f3d-109">数据： [Bool](xref:microsoft.quantum.lang-ref.bool)[] []</span><span class="sxs-lookup"><span data-stu-id="52f3d-109">data : [Bool](xref:microsoft.quantum.lang-ref.bool)[][]</span></span>




### <a name="keepcoeffregister--littleendian"></a><span data-ttu-id="52f3d-110">keepCoeffRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="52f3d-110">keepCoeffRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="altindexregister--littleendian"></a><span data-ttu-id="52f3d-111">altIndexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="52f3d-111">altIndexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="dataregister--qubit"></a><span data-ttu-id="52f3d-112">dataRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52f3d-112">dataRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="altdataregister--qubit"></a><span data-ttu-id="52f3d-113">altDataRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52f3d-113">altDataRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="52f3d-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52f3d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

