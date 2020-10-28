---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696089"
---
# <a name="controlledonint-function"></a><span data-ttu-id="c4981-102">ControlledOnInt 函数</span><span class="sxs-lookup"><span data-stu-id="c4981-102">ControlledOnInt function</span></span>

<span data-ttu-id="c4981-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4981-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4981-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4981-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4981-105">如果控件注册状态对应于指定的正整数，则返回一个单一运算符，该运算符应用目标寄存器上的 oracle。</span><span class="sxs-lookup"><span data-stu-id="c4981-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c4981-106">输入</span><span class="sxs-lookup"><span data-stu-id="c4981-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="c4981-107">numberState： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c4981-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c4981-108">正整数。</span><span class="sxs-lookup"><span data-stu-id="c4981-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="c4981-109">oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c4981-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c4981-110">单一运算符。</span><span class="sxs-lookup"><span data-stu-id="c4981-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="c4981-111">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，不) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c4981-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c4981-112">`oracle`当控件注册状态对应于数字状态时，应用于目标寄存器的单一运算符 `numberState` 。</span><span class="sxs-lookup"><span data-stu-id="c4981-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4981-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="c4981-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4981-114">找</span><span class="sxs-lookup"><span data-stu-id="c4981-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c4981-115">注解</span><span class="sxs-lookup"><span data-stu-id="c4981-115">Remarks</span></span>

<span data-ttu-id="c4981-116">的值 `numberState` 是使用小字节序编码来解释的。</span><span class="sxs-lookup"><span data-stu-id="c4981-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>