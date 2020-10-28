---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700788"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="e1ca5-102">OracleToDiscrete 函数</span><span class="sxs-lookup"><span data-stu-id="e1ca5-102">OracleToDiscrete function</span></span>

<span data-ttu-id="e1ca5-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="e1ca5-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="e1ca5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1ca5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1ca5-105">给定一个表示 "黑盒" oracle 的操作，将返回一个独立的 oracle，它表示重复多次的 "黑箱" oracle。</span><span class="sxs-lookup"><span data-stu-id="e1ca5-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="e1ca5-106">输入</span><span class="sxs-lookup"><span data-stu-id="e1ca5-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="e1ca5-107">blackBoxOracle： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="e1ca5-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e1ca5-108">要指数化的操作。</span><span class="sxs-lookup"><span data-stu-id="e1ca5-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="e1ca5-109">输出： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="e1ca5-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="e1ca5-110">部分应用于 "黑盒" oracle 的操作，该</span><span class="sxs-lookup"><span data-stu-id="e1ca5-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>