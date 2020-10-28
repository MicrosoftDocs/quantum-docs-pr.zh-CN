---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualReferenced has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 2d39f74c68e48d2f2b8003b76885c9444056f8d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695404"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="2b1f3-102">AssertOperationsEqualReferenced 操作</span><span class="sxs-lookup"><span data-stu-id="2b1f3-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="2b1f3-103">命名空间： [Microsoft.](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="2b1f3-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="2b1f3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b1f3-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="2b1f3-105">AssertOperationsEqualReferenced 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="2b1f3-105">AssertOperationsEqualReferenced has been deprecated.</span></span> <span data-ttu-id="2b1f3-106">请改用 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced>。</span><span class="sxs-lookup"><span data-stu-id="2b1f3-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.</span></span>
>
> <span data-ttu-id="2b1f3-107">请使用 @"microsoft.quantum.diagnostics.assertoperationsequalreferenced"。</span><span class="sxs-lookup"><span data-stu-id="2b1f3-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span></span>
> <span data-ttu-id="2b1f3-108">请注意，此操作的参数顺序已更改。</span><span class="sxs-lookup"><span data-stu-id="2b1f3-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="2b1f3-109">输入</span><span class="sxs-lookup"><span data-stu-id="2b1f3-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="2b1f3-110">实际： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b1f3-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="2b1f3-111">应为： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="2b1f3-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="2b1f3-112">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b1f3-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="2b1f3-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b1f3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

