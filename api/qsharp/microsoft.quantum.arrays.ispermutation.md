---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696495"
---
# <a name="ispermutation-function"></a><span data-ttu-id="e076c-102">IsPermutation 函数</span><span class="sxs-lookup"><span data-stu-id="e076c-102">IsPermutation function</span></span>

<span data-ttu-id="e076c-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e076c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e076c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e076c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e076c-105">当且仅当给定数组表示排列时，输出为 true。</span><span class="sxs-lookup"><span data-stu-id="e076c-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="e076c-106">说明</span><span class="sxs-lookup"><span data-stu-id="e076c-106">Description</span></span>

<span data-ttu-id="e076c-107">给定 `array` 长度的数组 `n` ，当且仅当中的每个整数仅出现一次时，才返回 true， `0` 这样就 `n - 1` `array` `array` 可以解释为元素上的排列方式 `n` 。</span><span class="sxs-lookup"><span data-stu-id="e076c-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="e076c-108">输入</span><span class="sxs-lookup"><span data-stu-id="e076c-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="e076c-109">permuation： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e076c-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e076c-110">一个数组，该数组可以是也可以不表示排列。</span><span class="sxs-lookup"><span data-stu-id="e076c-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e076c-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="e076c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="e076c-112">注解</span><span class="sxs-lookup"><span data-stu-id="e076c-112">Remarks</span></span>

<span data-ttu-id="e076c-113">长度为零的数组是完全的。</span><span class="sxs-lookup"><span data-stu-id="e076c-113">An array of length zero is trivially a permutation.</span></span>