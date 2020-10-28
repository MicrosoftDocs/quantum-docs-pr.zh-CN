---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696701"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="c55c3-102">MeasurePaulis 操作</span><span class="sxs-lookup"><span data-stu-id="c55c3-102">MeasurePaulis operation</span></span>

<span data-ttu-id="c55c3-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="c55c3-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="c55c3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c55c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c55c3-105">给定多 qubit Pauli 运算符的数组，使用指定的度量小工具测量每个运算符，然后返回结果的数组。</span><span class="sxs-lookup"><span data-stu-id="c55c3-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="c55c3-106">输入</span><span class="sxs-lookup"><span data-stu-id="c55c3-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="c55c3-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="c55c3-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="c55c3-108">要测量的多 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="c55c3-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c55c3-109">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c55c3-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c55c3-110">进行注册以衡量给定运算符。</span><span class="sxs-lookup"><span data-stu-id="c55c3-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="c55c3-111">小工具： ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]、 [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="c55c3-111">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="c55c3-112">执行给定多 qubit 运算符度量的操作。</span><span class="sxs-lookup"><span data-stu-id="c55c3-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c55c3-113">输出： __无效 <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="c55c3-113">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="c55c3-114">从测量上的每个元素获得的结果的数组 `paulis` `target` 。</span><span class="sxs-lookup"><span data-stu-id="c55c3-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>