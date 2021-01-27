---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841678"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="f61d0-102">ApplyMultiplyControlledLowDepthAnd 操作</span><span class="sxs-lookup"><span data-stu-id="f61d0-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="f61d0-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f61d0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f61d0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f61d0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f61d0-105">实现多控制的 Toffoli 入口，假定目标 qubit 初始化为0。</span><span class="sxs-lookup"><span data-stu-id="f61d0-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="f61d0-106">Adjoint 操作假定目标 qubit 将重置为0。</span><span class="sxs-lookup"><span data-stu-id="f61d0-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="f61d0-107">要求 Vny-rz-j42 深度为1，而 helper qubits 的数目在 qubits 数量上为指数。</span><span class="sxs-lookup"><span data-stu-id="f61d0-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f61d0-108">输入</span><span class="sxs-lookup"><span data-stu-id="f61d0-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="f61d0-109">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f61d0-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f61d0-110">控件 qubits</span><span class="sxs-lookup"><span data-stu-id="f61d0-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f61d0-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f61d0-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f61d0-112">目标 qubit</span><span class="sxs-lookup"><span data-stu-id="f61d0-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="f61d0-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f61d0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

