---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695514"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="aa010-102">EncodeIntoSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="aa010-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="aa010-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="aa010-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="aa010-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa010-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa010-105">一种编码操作，用于将未编码的量程寄存器映射到⟦7，1，3⟧ Steane 量程代码下的编码的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="aa010-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="aa010-106">输入</span><span class="sxs-lookup"><span data-stu-id="aa010-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="aa010-107">physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa010-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa010-108">保留未编码的量程状态的 qubit 寄存器</span><span class="sxs-lookup"><span data-stu-id="aa010-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="aa010-109">auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa010-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa010-110">Qubit 寄存器，它最初为零，并添加到量程系统以便可以执行编码操作</span><span class="sxs-lookup"><span data-stu-id="aa010-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="aa010-111">输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="aa010-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="aa010-112">应用 Steane 编码器后保持状态的量程寄存器</span><span class="sxs-lookup"><span data-stu-id="aa010-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="aa010-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa010-113">See Also</span></span>

- [<span data-ttu-id="aa010-114">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="aa010-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="aa010-115">ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="aa010-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)