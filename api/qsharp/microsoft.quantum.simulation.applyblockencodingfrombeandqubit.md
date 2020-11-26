---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingFromBEandQubit
title: ApplyBlockEncodingFromBEandQubit 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingFromBEandQubit
qsharp.summary: Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding
ms.openlocfilehash: 16d54a982b020f4d4ded5901ec07de44a2d09726
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229607"
---
# <a name="applyblockencodingfrombeandqubit-operation"></a><span data-ttu-id="37efe-102">ApplyBlockEncodingFromBEandQubit 操作</span><span class="sxs-lookup"><span data-stu-id="37efe-102">ApplyBlockEncodingFromBEandQubit operation</span></span>

<span data-ttu-id="37efe-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="37efe-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="37efe-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37efe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37efe-105"> ( # B1 LittleEndian，Qubit [] ) => ( # A4 的转换是调整 + Ctl) 到 BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="37efe-105">Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding</span></span>

```qsharp
operation ApplyBlockEncodingFromBEandQubit (op : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl), auxiliary : Qubit[], system : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="37efe-106">输入</span><span class="sxs-lookup"><span data-stu-id="37efe-106">Input</span></span>

### <a name="op--littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="37efe-107">op： ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="37efe-107">op : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="37efe-108">辅助： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="37efe-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="system--qubit"></a><span data-ttu-id="37efe-109">system： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="37efe-109">system : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="37efe-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37efe-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

