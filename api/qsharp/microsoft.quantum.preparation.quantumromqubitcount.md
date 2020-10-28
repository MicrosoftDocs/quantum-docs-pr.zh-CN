---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700412"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="ac854-102">QuantumROMQubitCount 函数</span><span class="sxs-lookup"><span data-stu-id="ac854-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="ac854-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ac854-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ac854-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac854-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac854-105">返回必须分配给返回的操作的 qubits 的总数 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="ac854-105">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="ac854-106">输入</span><span class="sxs-lookup"><span data-stu-id="ac854-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="ac854-107">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ac854-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ac854-108">目标错误 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="ac854-108">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="ac854-109">nCoeffs： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac854-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac854-110">在中指定的系数数 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="ac854-110">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="ac854-111">Output： ([int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) # A3</span><span class="sxs-lookup"><span data-stu-id="ac854-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="ac854-112">第一个参数</span><span class="sxs-lookup"><span data-stu-id="ac854-112">First parameter</span></span>

<span data-ttu-id="ac854-113">一个元组， `(x,(y,z))` 其中 `x = y + z` 是所分配的 qubits 总数， `y` 是寄存器的 qubits 数 `LittleEndian` ， `z` 是垃圾 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="ac854-113">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>