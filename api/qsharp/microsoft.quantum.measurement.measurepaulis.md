---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 4faaf78f24fa28ae5e4f701b80d9297c910b975e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194213"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="008b5-102">MeasurePaulis 操作</span><span class="sxs-lookup"><span data-stu-id="008b5-102">MeasurePaulis operation</span></span>

<span data-ttu-id="008b5-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="008b5-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="008b5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="008b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="008b5-105">给定多 qubit Pauli 运算符的数组，使用指定的度量小工具测量每个运算符，然后返回结果的数组。</span><span class="sxs-lookup"><span data-stu-id="008b5-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="008b5-106">输入</span><span class="sxs-lookup"><span data-stu-id="008b5-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="008b5-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="008b5-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="008b5-108">要测量的多 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="008b5-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="008b5-109">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="008b5-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="008b5-110">进行注册以衡量给定运算符。</span><span class="sxs-lookup"><span data-stu-id="008b5-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="008b5-111">小工具： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]、[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) =>__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="008b5-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="008b5-112">执行给定多 qubit 运算符度量的操作。</span><span class="sxs-lookup"><span data-stu-id="008b5-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="008b5-113">输出：__无效 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="008b5-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="008b5-114">从测量上的每个元素获得的结果的数组 `paulis` `target` 。</span><span class="sxs-lookup"><span data-stu-id="008b5-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>