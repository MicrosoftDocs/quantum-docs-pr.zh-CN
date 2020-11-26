---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225476"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="5e895-102">ApplyBlockEncodingByLCU 操作</span><span class="sxs-lookup"><span data-stu-id="5e895-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="5e895-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5e895-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5e895-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e895-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e895-105">`BlockEncodingByLCU` 的实现。</span><span class="sxs-lookup"><span data-stu-id="5e895-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5e895-106">输入</span><span class="sxs-lookup"><span data-stu-id="5e895-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="5e895-107">statePreparation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="5e895-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="5e895-108">选择器： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit)  为调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="5e895-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="5e895-109">辅助：不</span><span class="sxs-lookup"><span data-stu-id="5e895-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="5e895-110">系统：的</span><span class="sxs-lookup"><span data-stu-id="5e895-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="5e895-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e895-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5e895-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="5e895-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e895-113">找</span><span class="sxs-lookup"><span data-stu-id="5e895-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="5e895-114">我们</span><span class="sxs-lookup"><span data-stu-id="5e895-114">'S</span></span>

