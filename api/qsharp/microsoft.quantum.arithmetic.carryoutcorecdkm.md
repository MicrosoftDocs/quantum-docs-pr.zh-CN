---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 2065c767b341241d32e5ac06bcff0071cbadb266
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843329"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="4b784-102">CarryOutCoreCDKM 操作</span><span class="sxs-lookup"><span data-stu-id="4b784-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="4b784-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4b784-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4b784-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b784-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b784-105">RippleCarryAdderCDKM 中与上述 ApplyOuterCDKMAdder 操作一起使用的核心操作，即 conjugated，用于获取 RippleCarryAdderCDKM 的内部操作。</span><span class="sxs-lookup"><span data-stu-id="4b784-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="4b784-106">此操作计算执行 qubit，并对输入的部分应用一系列 NOT 入口 `ys` 。</span><span class="sxs-lookup"><span data-stu-id="4b784-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4b784-107">输入</span><span class="sxs-lookup"><span data-stu-id="4b784-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4b784-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4b784-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4b784-109">第一个 qubit 注册。</span><span class="sxs-lookup"><span data-stu-id="4b784-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="4b784-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4b784-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4b784-111">第二个 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="4b784-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="4b784-112">ancilla： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4b784-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4b784-113">传递给此操作的 RippleCarryAdderCDKM 中使用的 ancilla qubit。</span><span class="sxs-lookup"><span data-stu-id="4b784-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="4b784-114">携带： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4b784-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4b784-115">在 RippleCarryAdderCDKM 操作中执行 qubit。</span><span class="sxs-lookup"><span data-stu-id="4b784-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b784-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b784-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="4b784-117">参考</span><span class="sxs-lookup"><span data-stu-id="4b784-117">References</span></span>

- <span data-ttu-id="4b784-118">Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton： "A 新的量程波纹-携带加法线路"，2004。</span><span class="sxs-lookup"><span data-stu-id="4b784-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1