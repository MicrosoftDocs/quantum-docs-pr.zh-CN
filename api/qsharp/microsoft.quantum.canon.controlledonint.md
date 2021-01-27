---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840793"
---
# <a name="controlledonint-function"></a><span data-ttu-id="21643-102">ControlledOnInt 函数</span><span class="sxs-lookup"><span data-stu-id="21643-102">ControlledOnInt function</span></span>

<span data-ttu-id="21643-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="21643-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="21643-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21643-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21643-105">如果控件注册状态对应于指定的正整数，则返回一个单一运算符，该运算符应用目标寄存器上的 oracle。</span><span class="sxs-lookup"><span data-stu-id="21643-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="21643-106">输入</span><span class="sxs-lookup"><span data-stu-id="21643-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="21643-107">numberState： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21643-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21643-108">正整数。</span><span class="sxs-lookup"><span data-stu-id="21643-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="21643-109">oracle： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="21643-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="21643-110">单一运算符。</span><span class="sxs-lookup"><span data-stu-id="21643-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="21643-111">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，不) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="21643-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="21643-112">`oracle`当控件注册状态对应于数字状态时，应用于目标寄存器的单一运算符 `numberState` 。</span><span class="sxs-lookup"><span data-stu-id="21643-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="21643-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="21643-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="21643-114">找</span><span class="sxs-lookup"><span data-stu-id="21643-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="21643-115">备注</span><span class="sxs-lookup"><span data-stu-id="21643-115">Remarks</span></span>

<span data-ttu-id="21643-116">的值 `numberState` 是使用小字节序编码来解释的。</span><span class="sxs-lookup"><span data-stu-id="21643-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>