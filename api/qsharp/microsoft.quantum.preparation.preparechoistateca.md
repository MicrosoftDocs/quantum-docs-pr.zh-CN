---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: PrepareChoiStateCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: b9d2cdaea1ebc957719d92bf12901c54a55a56aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695093"
---
# <a name="preparechoistateca-operation"></a><span data-ttu-id="11873-102">PrepareChoiStateCA 操作</span><span class="sxs-lookup"><span data-stu-id="11873-102">PrepareChoiStateCA operation</span></span>

<span data-ttu-id="11873-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="11873-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="11873-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="11873-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="11873-105">为具有受控和 adjoint 变体的给定操作准备 Choi – Jamiłkowski 状态到给定的引用和目标寄存器。</span><span class="sxs-lookup"><span data-stu-id="11873-105">Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="11873-106">输入</span><span class="sxs-lookup"><span data-stu-id="11873-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="11873-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="11873-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="11873-108">参考： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="11873-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="11873-109">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="11873-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="11873-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11873-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="11873-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11873-111">See Also</span></span>

- [<span data-ttu-id="11873-112">PrepareChoiState。</span><span class="sxs-lookup"><span data-stu-id="11873-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)