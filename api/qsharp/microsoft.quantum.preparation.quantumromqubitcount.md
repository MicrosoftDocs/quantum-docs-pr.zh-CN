---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210397"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="1e536-102">QuantumROMQubitCount 函数</span><span class="sxs-lookup"><span data-stu-id="1e536-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="1e536-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="1e536-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="1e536-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e536-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="1e536-105">QuantumROMQubitCount 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="1e536-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="1e536-106">请改用 <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements>。</span><span class="sxs-lookup"><span data-stu-id="1e536-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="1e536-107">返回必须分配给返回的操作的 qubits 的总数 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="1e536-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="1e536-108">输入</span><span class="sxs-lookup"><span data-stu-id="1e536-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="1e536-109">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1e536-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1e536-110">目标错误 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="1e536-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="1e536-111">nCoeffs： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e536-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e536-112">在中指定的系数数 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="1e536-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="1e536-113">Output： ([int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) # A3</span><span class="sxs-lookup"><span data-stu-id="1e536-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="1e536-114">第一个参数</span><span class="sxs-lookup"><span data-stu-id="1e536-114">First parameter</span></span>

<span data-ttu-id="1e536-115">一个元组， `(x,(y,z))` 其中 `x = y + z` 是所分配的 qubits 总数， `y` 是寄存器的 qubits 数 `LittleEndian` ， `z` 是垃圾 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="1e536-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>