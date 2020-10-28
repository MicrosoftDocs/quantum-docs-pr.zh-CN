---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695862"
---
# <a name="isnotzero-function"></a><span data-ttu-id="0c9b6-102">IsNotZero 函数</span><span class="sxs-lookup"><span data-stu-id="0c9b6-102">IsNotZero function</span></span>

<span data-ttu-id="0c9b6-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0c9b6-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="0c9b6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c9b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c9b6-105">检查数字是否 `Double` 不约为零。</span><span class="sxs-lookup"><span data-stu-id="0c9b6-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="0c9b6-106">输入</span><span class="sxs-lookup"><span data-stu-id="0c9b6-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="0c9b6-107">number： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c9b6-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0c9b6-108">要检查的数字</span><span class="sxs-lookup"><span data-stu-id="0c9b6-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="0c9b6-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="0c9b6-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0c9b6-110">如果 `number` 的绝对值大于，则返回 true `1e-15` 。</span><span class="sxs-lookup"><span data-stu-id="0c9b6-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>