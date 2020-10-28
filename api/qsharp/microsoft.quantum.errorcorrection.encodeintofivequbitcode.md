---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695515"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="eb307-102">EncodeIntoFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="eb307-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="eb307-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="eb307-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="eb307-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb307-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb307-105">编码为⟦5，1，3⟧量程代码。</span><span class="sxs-lookup"><span data-stu-id="eb307-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="eb307-106">输入</span><span class="sxs-lookup"><span data-stu-id="eb307-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="eb307-107">physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eb307-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eb307-108">表示未编码状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="eb307-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="eb307-109">此数组 `Qubit[]` 的长度为1。</span><span class="sxs-lookup"><span data-stu-id="eb307-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="eb307-110">auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eb307-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eb307-111">将用于表示编码状态的辅助 qubits 的注册。</span><span class="sxs-lookup"><span data-stu-id="eb307-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="eb307-112">输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="eb307-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="eb307-113">存储编码状态的类型的物理 qubits 数组 `LogicalRegister` 。</span><span class="sxs-lookup"><span data-stu-id="eb307-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb307-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb307-114">See Also</span></span>

- [<span data-ttu-id="eb307-115">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="eb307-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)