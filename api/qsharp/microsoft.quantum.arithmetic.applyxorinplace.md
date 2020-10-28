---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699957"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="34934-102">ApplyXorInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="34934-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="34934-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="34934-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="34934-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34934-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34934-105">在传统整数和由 qubits 的寄存器表示的整数之间应用按位 "异或" 运算。</span><span class="sxs-lookup"><span data-stu-id="34934-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="34934-106">说明</span><span class="sxs-lookup"><span data-stu-id="34934-106">Description</span></span>

<span data-ttu-id="34934-107">将 `X` 操作应用到基于整数中的1位的小 endian 寄存器中的 qubits。</span><span class="sxs-lookup"><span data-stu-id="34934-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="34934-108">让我们表示， `value` 并使 y 成为编码的无符号整数 `target` ，然后 `InPlaceXorLE` 执行以下映射指定的操作： $ \ket{y}\rightarrow \ket{y\oplus a} $，其中 $ \oplus $ 为按位 "异或" 运算符。</span><span class="sxs-lookup"><span data-stu-id="34934-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="34934-109">输入</span><span class="sxs-lookup"><span data-stu-id="34934-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="34934-110">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34934-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34934-111">一个整数，其假定为非负数。</span><span class="sxs-lookup"><span data-stu-id="34934-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="34934-112">目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="34934-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="34934-113">用于存储 `value` 小字节序编码的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="34934-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="34934-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34934-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

