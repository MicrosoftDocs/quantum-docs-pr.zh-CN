---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193839"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="014d8-102">OracleToDiscrete 函数</span><span class="sxs-lookup"><span data-stu-id="014d8-102">OracleToDiscrete function</span></span>

<span data-ttu-id="014d8-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="014d8-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="014d8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="014d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="014d8-105">给定一个表示 "黑盒" oracle 的操作，将返回一个独立的 oracle，它表示重复多次的 "黑箱" oracle。</span><span class="sxs-lookup"><span data-stu-id="014d8-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="014d8-106">输入</span><span class="sxs-lookup"><span data-stu-id="014d8-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="014d8-107">blackBoxOracle： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="014d8-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="014d8-108">要指数化的操作。</span><span class="sxs-lookup"><span data-stu-id="014d8-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="014d8-109">输出： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="014d8-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="014d8-110">部分应用于 "黑盒" oracle 的操作，该</span><span class="sxs-lookup"><span data-stu-id="014d8-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>