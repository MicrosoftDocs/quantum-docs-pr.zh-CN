---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 70e52b7440dca1fa8761db13d6187cb6bf8c43c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200979"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="bf995-102">EncodeIntoFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="bf995-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="bf995-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="bf995-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="bf995-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf995-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf995-105">编码为⟦5，1，3⟧量程代码。</span><span class="sxs-lookup"><span data-stu-id="bf995-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="bf995-106">输入</span><span class="sxs-lookup"><span data-stu-id="bf995-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="bf995-107">physRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bf995-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bf995-108">表示未编码状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="bf995-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="bf995-109">此数组 `Qubit[]` 的长度为1。</span><span class="sxs-lookup"><span data-stu-id="bf995-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="bf995-110">auxQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bf995-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bf995-111">将用于表示编码状态的辅助 qubits 的注册。</span><span class="sxs-lookup"><span data-stu-id="bf995-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="bf995-112">输出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="bf995-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="bf995-113">存储编码状态的类型的物理 qubits 数组 `LogicalRegister` 。</span><span class="sxs-lookup"><span data-stu-id="bf995-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf995-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf995-114">See Also</span></span>

- [<span data-ttu-id="bf995-115">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="bf995-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)