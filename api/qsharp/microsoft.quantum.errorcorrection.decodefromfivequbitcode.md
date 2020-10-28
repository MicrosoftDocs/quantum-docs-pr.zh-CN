---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: DecodeFromFiveQubitCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 421da6296b604f30aefed58730091f64f19c3a61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695525"
---
# <a name="decodefromfivequbitcode-operation"></a><span data-ttu-id="93556-102">DecodeFromFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="93556-102">DecodeFromFiveQubitCode operation</span></span>

<span data-ttu-id="93556-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="93556-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="93556-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93556-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93556-105">对⟦5，1，3⟧量程代码进行解码。</span><span class="sxs-lookup"><span data-stu-id="93556-105">Decodes the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="93556-106">输入</span><span class="sxs-lookup"><span data-stu-id="93556-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="93556-107">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="93556-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="93556-108">表示已编码的 qubit 代码逻辑状态的 qubits 的数组。</span><span class="sxs-lookup"><span data-stu-id="93556-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="93556-109">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) </span><span class="sxs-lookup"><span data-stu-id="93556-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="93556-110">长度为1的 qubit 数组，它表示第一个参数中未编码的状态，以及第二个参数中的辅助 qubits。</span><span class="sxs-lookup"><span data-stu-id="93556-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="93556-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93556-111">See Also</span></span>

- [<span data-ttu-id="93556-112">ErrorCorrection. FiveQubitCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="93556-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [<span data-ttu-id="93556-113">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="93556-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)