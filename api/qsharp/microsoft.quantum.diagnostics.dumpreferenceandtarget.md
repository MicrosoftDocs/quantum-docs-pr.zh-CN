---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: f791f6f1e3c1b1da14ac3548a4bd78bb4f24ff83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695580"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="51b4d-102">DumpReferenceAndTarget 操作</span><span class="sxs-lookup"><span data-stu-id="51b4d-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="51b4d-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="51b4d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="51b4d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="51b4d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="51b4d-105">使用 DumpRegister 提供对引用和目标寄存器状态的诊断。</span><span class="sxs-lookup"><span data-stu-id="51b4d-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="51b4d-106">编写为单独的操作，以允许重写和解释为单独的寄存器，而不是作为单个合并寄存器。</span><span class="sxs-lookup"><span data-stu-id="51b4d-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="51b4d-107">输入</span><span class="sxs-lookup"><span data-stu-id="51b4d-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="51b4d-108">参考： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="51b4d-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="51b4d-109">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="51b4d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="51b4d-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51b4d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
