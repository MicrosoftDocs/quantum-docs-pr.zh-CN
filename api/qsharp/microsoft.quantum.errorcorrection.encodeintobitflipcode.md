---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 44034a864c946a7d3dbb21bad5ee500660709f1a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826682"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="f2420-102">EncodeIntoBitFlipCode 操作</span><span class="sxs-lookup"><span data-stu-id="f2420-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="f2420-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f2420-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f2420-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2420-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2420-105">编码为 [3，1，3]/⟦3，1，1⟧位翻转代码。</span><span class="sxs-lookup"><span data-stu-id="f2420-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="f2420-106">输入</span><span class="sxs-lookup"><span data-stu-id="f2420-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="f2420-107">physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f2420-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f2420-108">物理 qubits 的寄存器，表示要保护的数据。</span><span class="sxs-lookup"><span data-stu-id="f2420-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="f2420-109">auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f2420-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f2420-110">最初在 $ \ket $ 状态中注册辅助 qubits，用于对 {00} 要保护的数据进行编码。</span><span class="sxs-lookup"><span data-stu-id="f2420-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="f2420-111">输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="f2420-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="f2420-112">编码中使用的物理和辅助 qubits，用逻辑寄存器表示。</span><span class="sxs-lookup"><span data-stu-id="f2420-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2420-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2420-113">See Also</span></span>

- [<span data-ttu-id="f2420-114">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="f2420-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)