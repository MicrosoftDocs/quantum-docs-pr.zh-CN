---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: eb01b1b9fccc19f0e3f1fd5ee596b95d0d61563f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200537"
---
# <a name="recovercss-operation"></a><span data-ttu-id="7d741-102">RecoverCSS 操作</span><span class="sxs-lookup"><span data-stu-id="7d741-102">RecoverCSS operation</span></span>

<span data-ttu-id="7d741-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7d741-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7d741-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d741-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d741-105">按类型描述的量程代码执行一轮错误更正 `CSS` 。</span><span class="sxs-lookup"><span data-stu-id="7d741-105">Performs a single round of error correction by a quantum code described by a `CSS` type.</span></span>

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="7d741-106">输入</span><span class="sxs-lookup"><span data-stu-id="7d741-106">Input</span></span>

### <a name="code--css"></a><span data-ttu-id="7d741-107">代码： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="7d741-107">code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="7d741-108">封装为类型的量程 CSS 错误更正代码 `CSS` 描述了量程数据的编码和解码，以及如何测量 syndromes 错误。</span><span class="sxs-lookup"><span data-stu-id="7d741-108">A quantum CSS error-correcting code packaged as a `CSS` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fnx--recoveryfn"></a><span data-ttu-id="7d741-109">fnX： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="7d741-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="7d741-110">一个 `RecoveryFn` ，它将每个 $X $ 错误症状映射到 `Pauli[]` 更正检测到的错误的操作。</span><span class="sxs-lookup"><span data-stu-id="7d741-110">A `RecoveryFn` that maps each $X$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="fnz--recoveryfn"></a><span data-ttu-id="7d741-111">fnZ： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="7d741-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="7d741-112">一个 `RecoveryFn` ，它将每个 $Z $ 错误症状映射到 `Pauli[]` 更正检测到的错误的操作。</span><span class="sxs-lookup"><span data-stu-id="7d741-112">A `RecoveryFn` that maps each $Z$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="7d741-113">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="7d741-113">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="7d741-114">定义了稳定程序代码的 qubits 的数组。</span><span class="sxs-lookup"><span data-stu-id="7d741-114">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d741-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d741-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7d741-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d741-116">See Also</span></span>

- [<span data-ttu-id="7d741-117">ErrorCorrection。</span><span class="sxs-lookup"><span data-stu-id="7d741-117">Microsoft.Quantum.ErrorCorrection.CSS</span></span>](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [<span data-ttu-id="7d741-118">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="7d741-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="7d741-119">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="7d741-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)