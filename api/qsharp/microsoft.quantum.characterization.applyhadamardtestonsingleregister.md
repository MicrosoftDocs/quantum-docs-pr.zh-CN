---
uid: Microsoft.Quantum.Characterization.ApplyHadamardTestOnSingleRegister
title: ApplyHadamardTestOnSingleRegister 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ApplyHadamardTestOnSingleRegister
qsharp.summary: ''
ms.openlocfilehash: d61912d3681f7a6462f4b25aaf800483aecbee01
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204447"
---
# <a name="applyhadamardtestonsingleregister-operation"></a><span data-ttu-id="8e9b1-102">ApplyHadamardTestOnSingleRegister 操作</span><span class="sxs-lookup"><span data-stu-id="8e9b1-102">ApplyHadamardTestOnSingleRegister operation</span></span>

<span data-ttu-id="8e9b1-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="8e9b1-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="8e9b1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e9b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyHadamardTestOnSingleRegister (phaseShift : Bool, commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="8e9b1-105">输入</span><span class="sxs-lookup"><span data-stu-id="8e9b1-105">Input</span></span>

### <a name="phaseshift--bool"></a><span data-ttu-id="8e9b1-106">phaseShift： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8e9b1-106">phaseShift : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="8e9b1-107">commonPreparation： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="8e9b1-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="8e9b1-108">preparation1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="8e9b1-108">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="8e9b1-109">preparation2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="8e9b1-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="register--qubit"></a><span data-ttu-id="8e9b1-110">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8e9b1-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="8e9b1-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e9b1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

