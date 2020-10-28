---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701056"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="ff21c-102">FastHadamardTransformed 函数</span><span class="sxs-lookup"><span data-stu-id="ff21c-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="ff21c-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ff21c-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ff21c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff21c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff21c-105">{-1,1}使用 fisher-yates 的方法计算使用编码的布尔函数的 Hadamard 转换</span><span class="sxs-lookup"><span data-stu-id="ff21c-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="ff21c-106">输入</span><span class="sxs-lookup"><span data-stu-id="ff21c-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="ff21c-107">func： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ff21c-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ff21c-108">编码的事实数据表 {-1,1}</span><span class="sxs-lookup"><span data-stu-id="ff21c-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="ff21c-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ff21c-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ff21c-110">函数的 Spectral 系数</span><span class="sxs-lookup"><span data-stu-id="ff21c-110">Spectral coefficients of the function</span></span>