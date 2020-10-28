---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695583"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="344bd-102">DumpMachine 函数</span><span class="sxs-lookup"><span data-stu-id="344bd-102">DumpMachine function</span></span>

<span data-ttu-id="344bd-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="344bd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="344bd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="344bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="344bd-105">转储当前目标计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="344bd-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="344bd-106">输入</span><span class="sxs-lookup"><span data-stu-id="344bd-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="344bd-107">位置：否</span><span class="sxs-lookup"><span data-stu-id="344bd-107">location : 'T</span></span>

<span data-ttu-id="344bd-108">提供有关在何处生成计算机转储的信息。</span><span class="sxs-lookup"><span data-stu-id="344bd-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="344bd-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="344bd-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="344bd-110">无。</span><span class="sxs-lookup"><span data-stu-id="344bd-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="344bd-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="344bd-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="344bd-112">找</span><span class="sxs-lookup"><span data-stu-id="344bd-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="344bd-113">注解</span><span class="sxs-lookup"><span data-stu-id="344bd-113">Remarks</span></span>

<span data-ttu-id="344bd-114">此方法允许您将有关目标计算机的当前状态的信息转储到文件或其他位置。</span><span class="sxs-lookup"><span data-stu-id="344bd-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="344bd-115">生成的实际信息和的语义 `location` 特定于每个目标计算机。</span><span class="sxs-lookup"><span data-stu-id="344bd-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="344bd-116">但是，提供空元组作为位置 (`()`) 或仅省略 `location` 参数通常意味着将输出生成到控制台。</span><span class="sxs-lookup"><span data-stu-id="344bd-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="344bd-117">对于作为量程开发工具包的一部分分发的本地完整状态模拟器，此方法需要一个带有文件路径的字符串，它将波形函数编写为一维复数数组，其中每个元素都表示测量相应状态的概率的 amplitudes。</span><span class="sxs-lookup"><span data-stu-id="344bd-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>