---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839600"
---
# <a name="isnotzero-function"></a><span data-ttu-id="73dae-102">IsNotZero 函数</span><span class="sxs-lookup"><span data-stu-id="73dae-102">IsNotZero function</span></span>

<span data-ttu-id="73dae-103">命名空间 [：](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="73dae-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="73dae-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="73dae-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="73dae-105">检查数字是否 `Double` 不约为零。</span><span class="sxs-lookup"><span data-stu-id="73dae-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="73dae-106">输入</span><span class="sxs-lookup"><span data-stu-id="73dae-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="73dae-107">number： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73dae-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73dae-108">要检查的数字</span><span class="sxs-lookup"><span data-stu-id="73dae-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="73dae-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="73dae-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="73dae-110">如果 `number` 的绝对值大于，则返回 true `1e-15` 。</span><span class="sxs-lookup"><span data-stu-id="73dae-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>