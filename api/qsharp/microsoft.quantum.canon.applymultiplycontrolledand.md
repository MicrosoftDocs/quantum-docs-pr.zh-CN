---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: 17a757278500833bc5a5d0635af020cfe1fd569f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218387"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="3e33e-102">ApplyMultiplyControlledAnd 操作</span><span class="sxs-lookup"><span data-stu-id="3e33e-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="3e33e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3e33e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3e33e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e33e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e33e-105">实现多控制的 Toffoli 入口，假定目标 qubit 初始化为0。</span><span class="sxs-lookup"><span data-stu-id="3e33e-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="3e33e-106">Adjoint 操作假定目标 qubit 将重置为0。</span><span class="sxs-lookup"><span data-stu-id="3e33e-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="3e33e-107">输入</span><span class="sxs-lookup"><span data-stu-id="3e33e-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="3e33e-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e33e-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e33e-109">控件 qubits</span><span class="sxs-lookup"><span data-stu-id="3e33e-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3e33e-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3e33e-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3e33e-111">目标 qubit</span><span class="sxs-lookup"><span data-stu-id="3e33e-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e33e-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e33e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

