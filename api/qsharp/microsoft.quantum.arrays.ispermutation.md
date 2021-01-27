---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848100"
---
# <a name="ispermutation-function"></a><span data-ttu-id="c8904-102">IsPermutation 函数</span><span class="sxs-lookup"><span data-stu-id="c8904-102">IsPermutation function</span></span>

<span data-ttu-id="c8904-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c8904-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c8904-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8904-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8904-105">当且仅当给定数组表示排列时，输出为 true。</span><span class="sxs-lookup"><span data-stu-id="c8904-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="c8904-106">说明</span><span class="sxs-lookup"><span data-stu-id="c8904-106">Description</span></span>

<span data-ttu-id="c8904-107">给定 `array` 长度的数组 `n` ，当且仅当中的每个整数仅出现一次时，才返回 true， `0` 这样就 `n - 1` `array` `array` 可以解释为元素上的排列方式 `n` 。</span><span class="sxs-lookup"><span data-stu-id="c8904-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="c8904-108">输入</span><span class="sxs-lookup"><span data-stu-id="c8904-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="c8904-109">permuation： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c8904-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c8904-110">一个数组，该数组可以是也可以不表示排列。</span><span class="sxs-lookup"><span data-stu-id="c8904-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c8904-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="c8904-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="c8904-112">示例</span><span class="sxs-lookup"><span data-stu-id="c8904-112">Example</span></span>

<span data-ttu-id="c8904-113">以下 Q # 代码将打印消息 "所有诊断已成功完成"：</span><span class="sxs-lookup"><span data-stu-id="c8904-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="c8904-114">备注</span><span class="sxs-lookup"><span data-stu-id="c8904-114">Remarks</span></span>

<span data-ttu-id="c8904-115">长度为零的数组是完全的。</span><span class="sxs-lookup"><span data-stu-id="c8904-115">An array of length zero is trivially a permutation.</span></span>