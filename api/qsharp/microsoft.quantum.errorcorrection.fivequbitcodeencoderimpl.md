---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695506"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="24743-102">FiveQubitCodeEncoderImpl 操作</span><span class="sxs-lookup"><span data-stu-id="24743-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="24743-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="24743-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="24743-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24743-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24743-105">专用操作，用于实现 5 qubit 编码器和解码器。</span><span class="sxs-lookup"><span data-stu-id="24743-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="24743-106">输入</span><span class="sxs-lookup"><span data-stu-id="24743-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="24743-107">数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24743-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="24743-108">包含1个 qubit 的数组，这是输入 qubit。</span><span class="sxs-lookup"><span data-stu-id="24743-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="24743-109">草稿： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24743-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="24743-110">一个包含4个 qubits 的数组，其中增加了冗余性。</span><span class="sxs-lookup"><span data-stu-id="24743-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24743-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24743-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="24743-112">注解</span><span class="sxs-lookup"><span data-stu-id="24743-112">Remarks</span></span>

<span data-ttu-id="24743-113">选择的特定编码器是从 Kliuchnikov 和 Maslov，"Clifford 电路的优化"，Phys 88，052307 (2013) 中获取的。 https://arxiv.org/abs/1305.0810、图 4b) 和总共需要11个入口。</span><span class="sxs-lookup"><span data-stu-id="24743-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>