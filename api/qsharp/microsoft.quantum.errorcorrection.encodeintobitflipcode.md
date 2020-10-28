---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695516"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="9656e-102">EncodeIntoBitFlipCode 操作</span><span class="sxs-lookup"><span data-stu-id="9656e-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="9656e-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9656e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9656e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9656e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9656e-105">编码为 [3，1，3]/⟦3，1，1⟧位翻转代码。</span><span class="sxs-lookup"><span data-stu-id="9656e-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="9656e-106">输入</span><span class="sxs-lookup"><span data-stu-id="9656e-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="9656e-107">physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9656e-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9656e-108">物理 qubits 的寄存器，表示要保护的数据。</span><span class="sxs-lookup"><span data-stu-id="9656e-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="9656e-109">auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9656e-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9656e-110">最初在 $ \ket $ 状态中注册辅助 qubits，用于对 {00} 要保护的数据进行编码。</span><span class="sxs-lookup"><span data-stu-id="9656e-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="9656e-111">输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="9656e-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="9656e-112">编码中使用的物理和辅助 qubits，用逻辑寄存器表示。</span><span class="sxs-lookup"><span data-stu-id="9656e-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="9656e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9656e-113">See Also</span></span>

- [<span data-ttu-id="9656e-114">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="9656e-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)