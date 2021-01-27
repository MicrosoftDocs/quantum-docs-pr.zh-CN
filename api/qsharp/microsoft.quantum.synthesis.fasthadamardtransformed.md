---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855458"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="9a16b-102">FastHadamardTransformed 函数</span><span class="sxs-lookup"><span data-stu-id="9a16b-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="9a16b-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9a16b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9a16b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a16b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a16b-105">{-1,1}使用 fisher-yates 的方法计算使用编码的布尔函数的 Hadamard 转换</span><span class="sxs-lookup"><span data-stu-id="9a16b-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="9a16b-106">输入</span><span class="sxs-lookup"><span data-stu-id="9a16b-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="9a16b-107">func： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9a16b-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9a16b-108">编码的事实数据表 {-1,1}</span><span class="sxs-lookup"><span data-stu-id="9a16b-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="9a16b-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9a16b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9a16b-110">函数的 Spectral 系数</span><span class="sxs-lookup"><span data-stu-id="9a16b-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="9a16b-111">示例</span><span class="sxs-lookup"><span data-stu-id="9a16b-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```