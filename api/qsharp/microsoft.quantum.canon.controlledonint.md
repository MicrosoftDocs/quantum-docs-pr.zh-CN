---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207252"
---
# <a name="controlledonint-function"></a><span data-ttu-id="9a519-102">ControlledOnInt 函数</span><span class="sxs-lookup"><span data-stu-id="9a519-102">ControlledOnInt function</span></span>

<span data-ttu-id="9a519-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a519-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a519-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a519-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a519-105">如果控件注册状态对应于指定的正整数，则返回一个单一运算符，该运算符应用目标寄存器上的 oracle。</span><span class="sxs-lookup"><span data-stu-id="9a519-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9a519-106">输入</span><span class="sxs-lookup"><span data-stu-id="9a519-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="9a519-107">numberState： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a519-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a519-108">正整数。</span><span class="sxs-lookup"><span data-stu-id="9a519-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="9a519-109">oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9a519-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9a519-110">单一运算符。</span><span class="sxs-lookup"><span data-stu-id="9a519-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="9a519-111">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，不) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9a519-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9a519-112">`oracle`当控件注册状态对应于数字状态时，应用于目标寄存器的单一运算符 `numberState` 。</span><span class="sxs-lookup"><span data-stu-id="9a519-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9a519-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="9a519-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a519-114">找</span><span class="sxs-lookup"><span data-stu-id="9a519-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="9a519-115">备注</span><span class="sxs-lookup"><span data-stu-id="9a519-115">Remarks</span></span>

<span data-ttu-id="9a519-116">的值 `numberState` 是使用小字节序编码来解释的。</span><span class="sxs-lookup"><span data-stu-id="9a519-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>