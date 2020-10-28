---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700056"
---
# <a name="addi-operation"></a><span data-ttu-id="2607a-102">AddI 操作</span><span class="sxs-lookup"><span data-stu-id="2607a-102">AddI operation</span></span>

<span data-ttu-id="2607a-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2607a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2607a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2607a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2607a-105">根据的寄存器大小，自动选择 "执行" 和 "无" `ys` 。</span><span class="sxs-lookup"><span data-stu-id="2607a-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="2607a-106">输入</span><span class="sxs-lookup"><span data-stu-id="2607a-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="2607a-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2607a-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2607a-108">$n $ 加数。</span><span class="sxs-lookup"><span data-stu-id="2607a-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="2607a-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2607a-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2607a-110">至少 $n $ qubits 的加数。</span><span class="sxs-lookup"><span data-stu-id="2607a-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="2607a-111">将保存结果。</span><span class="sxs-lookup"><span data-stu-id="2607a-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2607a-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2607a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

