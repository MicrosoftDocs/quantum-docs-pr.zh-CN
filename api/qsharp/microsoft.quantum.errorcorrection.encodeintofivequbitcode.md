---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826324"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="2d500-102">EncodeIntoFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="2d500-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="2d500-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="2d500-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="2d500-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d500-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d500-105">编码为⟦5，1，3⟧量程代码。</span><span class="sxs-lookup"><span data-stu-id="2d500-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="2d500-106">输入</span><span class="sxs-lookup"><span data-stu-id="2d500-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="2d500-107">physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2d500-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2d500-108">表示未编码状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="2d500-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="2d500-109">此数组 `Qubit[]` 的长度为1。</span><span class="sxs-lookup"><span data-stu-id="2d500-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="2d500-110">auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2d500-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2d500-111">将用于表示编码状态的辅助 qubits 的注册。</span><span class="sxs-lookup"><span data-stu-id="2d500-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="2d500-112">输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="2d500-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="2d500-113">存储编码状态的类型的物理 qubits 数组 `LogicalRegister` 。</span><span class="sxs-lookup"><span data-stu-id="2d500-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d500-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d500-114">See Also</span></span>

- [<span data-ttu-id="2d500-115">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="2d500-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)