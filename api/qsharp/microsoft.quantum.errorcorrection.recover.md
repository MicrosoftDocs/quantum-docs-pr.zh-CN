---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 恢复操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695488"
---
# <a name="recover-operation"></a><span data-ttu-id="e6ad6-102">恢复操作</span><span class="sxs-lookup"><span data-stu-id="e6ad6-102">Recover operation</span></span>

<span data-ttu-id="e6ad6-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e6ad6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e6ad6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6ad6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6ad6-105">按类型描述的量程代码执行一轮错误更正 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="e6ad6-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="e6ad6-106">输入</span><span class="sxs-lookup"><span data-stu-id="e6ad6-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="e6ad6-107">代码： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="e6ad6-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="e6ad6-108">打包为类型的量程错误更正代码 `QECC` 描述了量程数据的编码和解码，以及如何测量 syndromes 错误。</span><span class="sxs-lookup"><span data-stu-id="e6ad6-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="e6ad6-109">fn： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="e6ad6-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="e6ad6-110">一个 `RecoveryFn` ，它将每个错误症状映射到 `Pauli[]` 更正检测到的错误的操作。</span><span class="sxs-lookup"><span data-stu-id="e6ad6-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="e6ad6-111">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="e6ad6-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="e6ad6-112">定义了稳定程序代码的 qubits 的数组。</span><span class="sxs-lookup"><span data-stu-id="e6ad6-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6ad6-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6ad6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e6ad6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6ad6-114">See Also</span></span>

- [<span data-ttu-id="e6ad6-115">ErrorCorrection. QECC</span><span class="sxs-lookup"><span data-stu-id="e6ad6-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="e6ad6-116">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="e6ad6-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="e6ad6-117">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="e6ad6-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)