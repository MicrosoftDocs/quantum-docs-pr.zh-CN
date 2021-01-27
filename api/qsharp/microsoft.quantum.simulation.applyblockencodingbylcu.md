---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852823"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="78e2f-102">ApplyBlockEncodingByLCU 操作</span><span class="sxs-lookup"><span data-stu-id="78e2f-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="78e2f-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="78e2f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="78e2f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78e2f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78e2f-105">`BlockEncodingByLCU` 的实现。</span><span class="sxs-lookup"><span data-stu-id="78e2f-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="78e2f-106">输入</span><span class="sxs-lookup"><span data-stu-id="78e2f-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="78e2f-107">statePreparation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="78e2f-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="78e2f-108">选择器： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit)  为调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="78e2f-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="78e2f-109">辅助：不</span><span class="sxs-lookup"><span data-stu-id="78e2f-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="78e2f-110">系统：的</span><span class="sxs-lookup"><span data-stu-id="78e2f-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="78e2f-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78e2f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="78e2f-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="78e2f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="78e2f-113">找</span><span class="sxs-lookup"><span data-stu-id="78e2f-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="78e2f-114">我们</span><span class="sxs-lookup"><span data-stu-id="78e2f-114">'S</span></span>

