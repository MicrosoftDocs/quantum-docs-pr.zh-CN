---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695485"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="7d63e-102">SteaneCodeEncoderImpl 操作</span><span class="sxs-lookup"><span data-stu-id="7d63e-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="7d63e-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7d63e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7d63e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7d63e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7d63e-105">专用操作，用于实现 Steane 代码编码器和解码器。</span><span class="sxs-lookup"><span data-stu-id="7d63e-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7d63e-106">输入</span><span class="sxs-lookup"><span data-stu-id="7d63e-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="7d63e-107">数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7d63e-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7d63e-108">包含1个 qubit 的数组，这是输入 qubit。</span><span class="sxs-lookup"><span data-stu-id="7d63e-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="7d63e-109">草稿： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7d63e-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7d63e-110">包含6个 qubits 的数组，这会增加冗余性。</span><span class="sxs-lookup"><span data-stu-id="7d63e-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d63e-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d63e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

