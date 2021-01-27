---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826204"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="23218-102">EncodeIntoSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="23218-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="23218-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="23218-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="23218-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23218-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23218-105">一种编码操作，用于将未编码的量程寄存器映射到⟦7，1，3⟧ Steane 量程代码下的编码的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="23218-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="23218-106">输入</span><span class="sxs-lookup"><span data-stu-id="23218-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="23218-107">physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="23218-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="23218-108">保留未编码的量程状态的 qubit 寄存器</span><span class="sxs-lookup"><span data-stu-id="23218-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="23218-109">auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="23218-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="23218-110">Qubit 寄存器，它最初为零，并添加到量程系统以便可以执行编码操作</span><span class="sxs-lookup"><span data-stu-id="23218-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="23218-111">输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="23218-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="23218-112">应用 Steane 编码器后保持状态的量程寄存器</span><span class="sxs-lookup"><span data-stu-id="23218-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="23218-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23218-113">See Also</span></span>

- [<span data-ttu-id="23218-114">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="23218-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="23218-115">ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="23218-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)