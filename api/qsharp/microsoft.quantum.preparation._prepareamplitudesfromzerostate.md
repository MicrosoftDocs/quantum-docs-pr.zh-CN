---
uid: Microsoft.Quantum.Preparation._PrepareAmplitudesFromZeroState
title: _PrepareAmplitudesFromZeroState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _PrepareAmplitudesFromZeroState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients. Uses state emulation if supported by the target.
ms.openlocfilehash: 3d90b455bace7b0de1c8c01a5b9b007d719df950
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226581"
---
# <a name="_prepareamplitudesfromzerostate-operation"></a><span data-ttu-id="dd7a2-102">_PrepareAmplitudesFromZeroState 操作</span><span class="sxs-lookup"><span data-stu-id="dd7a2-102">_PrepareAmplitudesFromZeroState operation</span></span>

<span data-ttu-id="dd7a2-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="dd7a2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="dd7a2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd7a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd7a2-105">给定一组系数和一个小 endian 编码的 unentangled qubits 的量程注册，所有这些都处于零状态，并准备由给定系数描述的该寄存器上的状态。</span><span class="sxs-lookup"><span data-stu-id="dd7a2-105">Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients.</span></span> <span data-ttu-id="dd7a2-106">如果目标支持，则使用状态模拟。</span><span class="sxs-lookup"><span data-stu-id="dd7a2-106">Uses state emulation if supported by the target.</span></span>

```qsharp
operation _PrepareAmplitudesFromZeroState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="dd7a2-107">输入</span><span class="sxs-lookup"><span data-stu-id="dd7a2-107">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="dd7a2-108">系数： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="dd7a2-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>




### <a name="qubits--littleendian"></a><span data-ttu-id="dd7a2-109">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dd7a2-109">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="dd7a2-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd7a2-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

