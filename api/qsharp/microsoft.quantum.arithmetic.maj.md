---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699832"
---
# <a name="maj-operation"></a><span data-ttu-id="61837-102">MAJ 操作</span><span class="sxs-lookup"><span data-stu-id="61837-102">MAJ operation</span></span>

<span data-ttu-id="61837-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="61837-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="61837-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="61837-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="61837-105">这会将就地大多数操作应用到 3 qubits。</span><span class="sxs-lookup"><span data-stu-id="61837-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="61837-106">说明</span><span class="sxs-lookup"><span data-stu-id="61837-106">Description</span></span>

<span data-ttu-id="61837-107">如果将目标 qubit 的状态指示为 $ \ket{z} $，并将输入 qubits 输入状态输入为 $ \ket{x} $ 和 $ \ket{y} $，则此操作将执行以下转换： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x、y、z) } $。</span><span class="sxs-lookup"><span data-stu-id="61837-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="61837-108">输入</span><span class="sxs-lookup"><span data-stu-id="61837-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="61837-109">input0： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="61837-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="61837-110">第一个输入 qubit。</span><span class="sxs-lookup"><span data-stu-id="61837-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="61837-111">input1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="61837-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="61837-112">第二个输入 qubit。</span><span class="sxs-lookup"><span data-stu-id="61837-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="61837-113">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="61837-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="61837-114">将应用多数函数的 qubit。</span><span class="sxs-lookup"><span data-stu-id="61837-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61837-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61837-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

