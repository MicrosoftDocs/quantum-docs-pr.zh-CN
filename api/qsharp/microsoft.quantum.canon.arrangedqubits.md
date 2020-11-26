---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217061"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="e86f1-102">ArrangedQubits 函数</span><span class="sxs-lookup"><span data-stu-id="e86f1-102">ArrangedQubits function</span></span>

<span data-ttu-id="e86f1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e86f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e86f1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e86f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e86f1-105">根据索引排列 control、target 和 helper qubits</span><span class="sxs-lookup"><span data-stu-id="e86f1-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="e86f1-106">描述</span><span class="sxs-lookup"><span data-stu-id="e86f1-106">Description</span></span>

<span data-ttu-id="e86f1-107">返回一个 Qubit 数组，其目标位于索引0，并在索引 2 ^ i 处控制 i。</span><span class="sxs-lookup"><span data-stu-id="e86f1-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="e86f1-108">帮助器 qubits 将被插入到数组中的其他所有位置。</span><span class="sxs-lookup"><span data-stu-id="e86f1-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="e86f1-109">输入</span><span class="sxs-lookup"><span data-stu-id="e86f1-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="e86f1-110">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e86f1-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="e86f1-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e86f1-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="e86f1-112">helper： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e86f1-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="e86f1-113">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e86f1-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

