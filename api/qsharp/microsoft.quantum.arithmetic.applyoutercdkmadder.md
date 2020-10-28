---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700016"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="943f9-102">ApplyOuterCDKMAdder 操作</span><span class="sxs-lookup"><span data-stu-id="943f9-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="943f9-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="943f9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="943f9-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="943f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="943f9-105">在下面的整数加法运算中使用的可逆的就地波纹-携带运算 RippleCarryAdderCDKM。</span><span class="sxs-lookup"><span data-stu-id="943f9-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="943f9-106">假设有两个 qubit 寄存器， `xs` 并且 `ys` 具有相同的长度，则操作会将 CNOT-CONTAINS 和 CCNOT 入口序列应用到中的 qubits， `xs` 并将 `ys` 作为目标中的控件和 qubits `xs` 。</span><span class="sxs-lookup"><span data-stu-id="943f9-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="943f9-107">输入</span><span class="sxs-lookup"><span data-stu-id="943f9-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="943f9-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="943f9-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="943f9-109">第一个 qubit 寄存器，其中包含控件和目标。</span><span class="sxs-lookup"><span data-stu-id="943f9-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="943f9-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="943f9-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="943f9-111">第二个 qubit 注册，对控件构成。</span><span class="sxs-lookup"><span data-stu-id="943f9-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="943f9-112">ancilla： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="943f9-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="943f9-113">传递给此操作的 RippleCarryAdderCDKM 中使用的 ancilla qubit。</span><span class="sxs-lookup"><span data-stu-id="943f9-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="943f9-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="943f9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="943f9-115">参考</span><span class="sxs-lookup"><span data-stu-id="943f9-115">References</span></span>

- <span data-ttu-id="943f9-116">Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton： "A 新的量程波纹-携带加法线路"，2004。</span><span class="sxs-lookup"><span data-stu-id="943f9-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1