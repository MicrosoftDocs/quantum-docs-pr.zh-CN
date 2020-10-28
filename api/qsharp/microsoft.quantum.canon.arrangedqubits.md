---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696136"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="5b637-102">ArrangedQubits 函数</span><span class="sxs-lookup"><span data-stu-id="5b637-102">ArrangedQubits function</span></span>

<span data-ttu-id="5b637-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5b637-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5b637-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5b637-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5b637-105">根据索引排列 control、target 和 helper qubits</span><span class="sxs-lookup"><span data-stu-id="5b637-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="5b637-106">说明</span><span class="sxs-lookup"><span data-stu-id="5b637-106">Description</span></span>

<span data-ttu-id="5b637-107">返回一个 Qubit 数组，其目标位于索引0，并在索引 2 ^ i 处控制 i。</span><span class="sxs-lookup"><span data-stu-id="5b637-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="5b637-108">帮助器 qubits 将被插入到数组中的其他所有位置。</span><span class="sxs-lookup"><span data-stu-id="5b637-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="5b637-109">输入</span><span class="sxs-lookup"><span data-stu-id="5b637-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="5b637-110">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5b637-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="5b637-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5b637-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="5b637-112">helper： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5b637-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="5b637-113">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5b637-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

