---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: ApplyToLittleEndian 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: 1194ac369d2d474330357d26dd22709e9c68dd6e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226479"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="8cce7-102">ApplyToLittleEndian 操作</span><span class="sxs-lookup"><span data-stu-id="8cce7-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="8cce7-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8cce7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8cce7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8cce7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8cce7-105">将操作应用于生成小 endian 寄存器的基础 qubits。</span><span class="sxs-lookup"><span data-stu-id="8cce7-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="8cce7-106">此操作被标记为内部，因为小 endian 寄存器旨在 "不透明"，因此这只是实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="8cce7-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8cce7-107">输入</span><span class="sxs-lookup"><span data-stu-id="8cce7-107">Input</span></span>

### <a name="bareop--qubit--unit--is-adj--ctl"></a><span data-ttu-id="8cce7-108">bareOp： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="8cce7-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="8cce7-109">register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8cce7-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="8cce7-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8cce7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

