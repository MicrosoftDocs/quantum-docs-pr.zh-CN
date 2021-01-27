---
uid: Microsoft.Quantum.Preparation.WriteQuantumROMBitString
title: WriteQuantumROMBitString 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: WriteQuantumROMBitString
qsharp.summary: ''
ms.openlocfilehash: 3e4bed7656732f40f413149ea81024efffebfb62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855820"
---
# <a name="writequantumrombitstring-operation"></a><span data-ttu-id="315b0-102">WriteQuantumROMBitString 操作</span><span class="sxs-lookup"><span data-stu-id="315b0-102">WriteQuantumROMBitString operation</span></span>

<span data-ttu-id="315b0-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="315b0-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="315b0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="315b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation WriteQuantumROMBitString (idx : Int, keepCoeff : Int[], altIndex : Int[], data : Bool[][], keepCoeffRegister : Microsoft.Quantum.Arithmetic.LittleEndian, altIndexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, dataRegister : Qubit[], altDataRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="315b0-105">输入</span><span class="sxs-lookup"><span data-stu-id="315b0-105">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="315b0-106">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="315b0-106">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="keepcoeff--int"></a><span data-ttu-id="315b0-107">keepCoeff： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="315b0-107">keepCoeff : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="altindex--int"></a><span data-ttu-id="315b0-108">altIndex： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="315b0-108">altIndex : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="data--bool"></a><span data-ttu-id="315b0-109">数据： [Bool](xref:microsoft.quantum.lang-ref.bool)[] []</span><span class="sxs-lookup"><span data-stu-id="315b0-109">data : [Bool](xref:microsoft.quantum.lang-ref.bool)[][]</span></span>




### <a name="keepcoeffregister--littleendian"></a><span data-ttu-id="315b0-110">keepCoeffRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="315b0-110">keepCoeffRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="altindexregister--littleendian"></a><span data-ttu-id="315b0-111">altIndexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="315b0-111">altIndexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="dataregister--qubit"></a><span data-ttu-id="315b0-112">dataRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="315b0-112">dataRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="altdataregister--qubit"></a><span data-ttu-id="315b0-113">altDataRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="315b0-113">altDataRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="315b0-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="315b0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

