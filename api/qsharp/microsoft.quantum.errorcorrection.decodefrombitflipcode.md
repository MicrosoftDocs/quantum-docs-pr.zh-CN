---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: DecodeFromBitFlipCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695527"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="a4094-102">DecodeFromBitFlipCode 操作</span><span class="sxs-lookup"><span data-stu-id="a4094-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="a4094-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a4094-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a4094-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4094-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4094-105">从 [3，1，3]/⟦3，1，1⟧位翻转代码进行解码。</span><span class="sxs-lookup"><span data-stu-id="a4094-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="a4094-106">输入</span><span class="sxs-lookup"><span data-stu-id="a4094-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="a4094-107">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="a4094-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="a4094-108">位翻转代码的代码块。</span><span class="sxs-lookup"><span data-stu-id="a4094-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="a4094-109">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) </span><span class="sxs-lookup"><span data-stu-id="a4094-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="a4094-110">编码到逻辑寄存器中的数据的元组，以及用于表示症状的辅助 qubits。</span><span class="sxs-lookup"><span data-stu-id="a4094-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4094-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4094-111">See Also</span></span>

- [<span data-ttu-id="a4094-112">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="a4094-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="a4094-113">ErrorCorrection. EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="a4094-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)