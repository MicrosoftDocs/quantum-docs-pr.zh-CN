---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696309"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="6df18-102">ApplyMultiplyControlledAnd 操作</span><span class="sxs-lookup"><span data-stu-id="6df18-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="6df18-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6df18-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6df18-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6df18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6df18-105">实现多控制的 Toffoli 入口，假定目标 qubit 初始化为0。</span><span class="sxs-lookup"><span data-stu-id="6df18-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="6df18-106">Adjoint 操作假定目标 qubit 将重置为0。</span><span class="sxs-lookup"><span data-stu-id="6df18-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6df18-107">输入</span><span class="sxs-lookup"><span data-stu-id="6df18-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="6df18-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6df18-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6df18-109">控件 qubits</span><span class="sxs-lookup"><span data-stu-id="6df18-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6df18-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6df18-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6df18-111">目标 qubit</span><span class="sxs-lookup"><span data-stu-id="6df18-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="6df18-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6df18-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

