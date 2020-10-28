---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700181"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="1f9cc-102">ApplyBlockEncodingByLCU 操作</span><span class="sxs-lookup"><span data-stu-id="1f9cc-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="1f9cc-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1f9cc-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1f9cc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f9cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f9cc-105">`BlockEncodingByLCU` 的实现。</span><span class="sxs-lookup"><span data-stu-id="1f9cc-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a><span data-ttu-id="1f9cc-106">输入</span><span class="sxs-lookup"><span data-stu-id="1f9cc-106">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="1f9cc-107">statePreparation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1f9cc-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="1f9cc-108">选择器： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1f9cc-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="1f9cc-109">辅助：不</span><span class="sxs-lookup"><span data-stu-id="1f9cc-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="1f9cc-110">系统：的</span><span class="sxs-lookup"><span data-stu-id="1f9cc-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="1f9cc-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f9cc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1f9cc-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="1f9cc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1f9cc-113">找</span><span class="sxs-lookup"><span data-stu-id="1f9cc-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="1f9cc-114">我们</span><span class="sxs-lookup"><span data-stu-id="1f9cc-114">'S</span></span>

