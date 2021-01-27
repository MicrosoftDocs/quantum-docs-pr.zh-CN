---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 恢复操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: 3e2ce404ae3a6b4097897b859388fea3f915232c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825521"
---
# <a name="recover-operation"></a><span data-ttu-id="ac948-102">恢复操作</span><span class="sxs-lookup"><span data-stu-id="ac948-102">Recover operation</span></span>

<span data-ttu-id="ac948-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ac948-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ac948-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac948-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac948-105">按类型描述的量程代码执行一轮错误更正 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="ac948-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="ac948-106">输入</span><span class="sxs-lookup"><span data-stu-id="ac948-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="ac948-107">代码： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="ac948-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="ac948-108">打包为类型的量程错误更正代码 `QECC` 描述了量程数据的编码和解码，以及如何测量 syndromes 错误。</span><span class="sxs-lookup"><span data-stu-id="ac948-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="ac948-109">fn： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="ac948-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="ac948-110">一个 `RecoveryFn` ，它将每个错误症状映射到 `Pauli[]` 更正检测到的错误的操作。</span><span class="sxs-lookup"><span data-stu-id="ac948-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="ac948-111">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="ac948-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="ac948-112">定义了稳定程序代码的 qubits 的数组。</span><span class="sxs-lookup"><span data-stu-id="ac948-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac948-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac948-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ac948-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac948-114">See Also</span></span>

- [<span data-ttu-id="ac948-115">ErrorCorrection. QECC</span><span class="sxs-lookup"><span data-stu-id="ac948-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="ac948-116">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="ac948-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="ac948-117">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="ac948-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)