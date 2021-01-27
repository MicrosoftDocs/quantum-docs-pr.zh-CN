---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846544"
---
# <a name="maj-operation"></a><span data-ttu-id="8bbb1-102">MAJ 操作</span><span class="sxs-lookup"><span data-stu-id="8bbb1-102">MAJ operation</span></span>

<span data-ttu-id="8bbb1-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8bbb1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8bbb1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8bbb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8bbb1-105">这会将就地大多数操作应用到 3 qubits。</span><span class="sxs-lookup"><span data-stu-id="8bbb1-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8bbb1-106">说明</span><span class="sxs-lookup"><span data-stu-id="8bbb1-106">Description</span></span>

<span data-ttu-id="8bbb1-107">如果将目标 qubit 的状态指示为 $ \ket{z} $，并将输入 qubits 输入状态输入为 $ \ket{x} $ 和 $ \ket{y} $，则此操作将执行以下转换： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x、y、z) } $。</span><span class="sxs-lookup"><span data-stu-id="8bbb1-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="8bbb1-108">输入</span><span class="sxs-lookup"><span data-stu-id="8bbb1-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="8bbb1-109">input0： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8bbb1-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8bbb1-110">第一个输入 qubit。</span><span class="sxs-lookup"><span data-stu-id="8bbb1-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="8bbb1-111">input1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8bbb1-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8bbb1-112">第二个输入 qubit。</span><span class="sxs-lookup"><span data-stu-id="8bbb1-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8bbb1-113">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8bbb1-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8bbb1-114">将应用多数函数的 qubit。</span><span class="sxs-lookup"><span data-stu-id="8bbb1-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8bbb1-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8bbb1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

