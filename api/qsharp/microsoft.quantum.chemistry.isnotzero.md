---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204056"
---
# <a name="isnotzero-function"></a><span data-ttu-id="4340e-102">IsNotZero 函数</span><span class="sxs-lookup"><span data-stu-id="4340e-102">IsNotZero function</span></span>

<span data-ttu-id="4340e-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4340e-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="4340e-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4340e-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4340e-105">检查数字是否 `Double` 不约为零。</span><span class="sxs-lookup"><span data-stu-id="4340e-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="4340e-106">输入</span><span class="sxs-lookup"><span data-stu-id="4340e-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="4340e-107">number： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4340e-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4340e-108">要检查的数字</span><span class="sxs-lookup"><span data-stu-id="4340e-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="4340e-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="4340e-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4340e-110">如果 `number` 的绝对值大于，则返回 true `1e-15` 。</span><span class="sxs-lookup"><span data-stu-id="4340e-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>