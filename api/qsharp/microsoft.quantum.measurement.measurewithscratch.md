---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227057"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="1317c-102">MeasureWithScratch 操作</span><span class="sxs-lookup"><span data-stu-id="1317c-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="1317c-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="1317c-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="1317c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1317c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1317c-105">使用显式暂存 qubit 度量给定的 Pauli 运算符以执行测量。</span><span class="sxs-lookup"><span data-stu-id="1317c-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="1317c-106">输入</span><span class="sxs-lookup"><span data-stu-id="1317c-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="1317c-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1317c-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1317c-108">指定为单一 qubit Pauli 运算符数组的多 qubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="1317c-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1317c-109">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1317c-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1317c-110">要测量的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="1317c-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1317c-111">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="1317c-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="1317c-112">在收银机上测量给定 Pauli 运算符的结果 `target` 。</span><span class="sxs-lookup"><span data-stu-id="1317c-112">The result of measuring the given Pauli operator on the `target` register.</span></span>