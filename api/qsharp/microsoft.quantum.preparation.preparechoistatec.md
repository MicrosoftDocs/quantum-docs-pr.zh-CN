---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateC
title: PrepareChoiStateC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateC
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with a controlled variant onto given reference and target registers.
ms.openlocfilehash: 34bb8eaebbc627d246e32a3cffd877ccad45e86e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854389"
---
# <a name="preparechoistatec-operation"></a><span data-ttu-id="a3a46-102">PrepareChoiStateC 操作</span><span class="sxs-lookup"><span data-stu-id="a3a46-102">PrepareChoiStateC operation</span></span>

<span data-ttu-id="a3a46-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a3a46-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a3a46-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3a46-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3a46-105">针对给定的引用和目标寄存器，为具有受控变体的给定操作准备 Choi – Jamiołkowski 状态。</span><span class="sxs-lookup"><span data-stu-id="a3a46-105">Prepares the Choi–Jamiołkowski state for a given operation with a controlled variant onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateC (op : (Qubit[] => Unit is Ctl), reference : Qubit[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="a3a46-106">输入</span><span class="sxs-lookup"><span data-stu-id="a3a46-106">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="a3a46-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="a3a46-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="a3a46-108">参考： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a3a46-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="a3a46-109">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a3a46-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="a3a46-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3a46-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a3a46-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3a46-111">See Also</span></span>

- [<span data-ttu-id="a3a46-112">PrepareChoiState。</span><span class="sxs-lookup"><span data-stu-id="a3a46-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)