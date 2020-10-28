---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695578"
---
# <a name="dumpregister-function"></a><span data-ttu-id="a7faf-102">DumpRegister 函数</span><span class="sxs-lookup"><span data-stu-id="a7faf-102">DumpRegister function</span></span>

<span data-ttu-id="a7faf-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a7faf-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a7faf-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a7faf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a7faf-105">将当前目标计算机的状态转储为与给定的 qubits 相关联。</span><span class="sxs-lookup"><span data-stu-id="a7faf-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a7faf-106">输入</span><span class="sxs-lookup"><span data-stu-id="a7faf-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="a7faf-107">位置：否</span><span class="sxs-lookup"><span data-stu-id="a7faf-107">location : 'T</span></span>

<span data-ttu-id="a7faf-108">提供有关在何处生成状态转储的信息。</span><span class="sxs-lookup"><span data-stu-id="a7faf-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a7faf-109">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a7faf-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a7faf-110">要报告的 qubits 的列表。</span><span class="sxs-lookup"><span data-stu-id="a7faf-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7faf-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7faf-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="a7faf-112">无。</span><span class="sxs-lookup"><span data-stu-id="a7faf-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a7faf-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="a7faf-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7faf-114">找</span><span class="sxs-lookup"><span data-stu-id="a7faf-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="a7faf-115">注解</span><span class="sxs-lookup"><span data-stu-id="a7faf-115">Remarks</span></span>

<span data-ttu-id="a7faf-116">此方法允许你将与给定 qubits 的状态关联的信息转储到一个文件或其他位置。</span><span class="sxs-lookup"><span data-stu-id="a7faf-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="a7faf-117">生成的实际信息和的语义 `location` 特定于每个目标计算机。</span><span class="sxs-lookup"><span data-stu-id="a7faf-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="a7faf-118">但是，将空元组作为位置 (提供 `()`) 通常表示生成到控制台的输出。</span><span class="sxs-lookup"><span data-stu-id="a7faf-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="a7faf-119">对于作为量程开发工具包的一部分分发的本地完整状态模拟器，此方法需要一个字符串路径与文件的路径，在该文件中，它将写入给定)  (qubits 的状态，其中，每个元素都表示测量相应状态的概率的 amplitudes，其中每个元素表示测量相应状态的概率的。</span><span class="sxs-lookup"><span data-stu-id="a7faf-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="a7faf-120">如果给定的 qubits 与一些其他 qubit 放大，且无法分离其状态，则只会报告 qubits 为放大。</span><span class="sxs-lookup"><span data-stu-id="a7faf-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>