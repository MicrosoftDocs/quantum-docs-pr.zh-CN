---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: ac3972287d55ed2df85e1d88510918cc5202c711
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844844"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="e2056-102">ApplyMultiplyControlledAnd 操作</span><span class="sxs-lookup"><span data-stu-id="e2056-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="e2056-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2056-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2056-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2056-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2056-105">实现多控制的 Toffoli 入口，假定目标 qubit 初始化为0。</span><span class="sxs-lookup"><span data-stu-id="e2056-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="e2056-106">Adjoint 操作假定目标 qubit 将重置为0。</span><span class="sxs-lookup"><span data-stu-id="e2056-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="e2056-107">输入</span><span class="sxs-lookup"><span data-stu-id="e2056-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="e2056-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e2056-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e2056-109">控件 qubits</span><span class="sxs-lookup"><span data-stu-id="e2056-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e2056-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e2056-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e2056-111">目标 qubit</span><span class="sxs-lookup"><span data-stu-id="e2056-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2056-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2056-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

