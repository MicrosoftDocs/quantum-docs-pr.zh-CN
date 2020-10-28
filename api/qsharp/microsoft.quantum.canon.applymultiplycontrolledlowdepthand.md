---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696308"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="87a23-102">ApplyMultiplyControlledLowDepthAnd 操作</span><span class="sxs-lookup"><span data-stu-id="87a23-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="87a23-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87a23-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87a23-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87a23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87a23-105">实现多控制的 Toffoli 入口，假定目标 qubit 初始化为0。</span><span class="sxs-lookup"><span data-stu-id="87a23-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="87a23-106">Adjoint 操作假定目标 qubit 将重置为0。</span><span class="sxs-lookup"><span data-stu-id="87a23-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="87a23-107">要求 Vny-rz-j42 深度为1，而 helper qubits 的数目在 qubits 数量上为指数。</span><span class="sxs-lookup"><span data-stu-id="87a23-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="87a23-108">输入</span><span class="sxs-lookup"><span data-stu-id="87a23-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="87a23-109">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="87a23-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="87a23-110">控件 qubits</span><span class="sxs-lookup"><span data-stu-id="87a23-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="87a23-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="87a23-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="87a23-112">目标 qubit</span><span class="sxs-lookup"><span data-stu-id="87a23-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="87a23-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87a23-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

