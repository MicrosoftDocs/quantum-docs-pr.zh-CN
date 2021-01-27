---
uid: Microsoft.Quantum.Synthesis.Extended
title: 扩展函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855471"
---
# <a name="extended-function"></a><span data-ttu-id="7ff57-102">扩展函数</span><span class="sxs-lookup"><span data-stu-id="7ff57-102">Extended function</span></span>

<span data-ttu-id="7ff57-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="7ff57-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="7ff57-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ff57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ff57-105">通过反转系数扩展色谱</span><span class="sxs-lookup"><span data-stu-id="7ff57-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="7ff57-106">输入</span><span class="sxs-lookup"><span data-stu-id="7ff57-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="7ff57-107">色谱： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7ff57-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7ff57-108">Spectral 系数</span><span class="sxs-lookup"><span data-stu-id="7ff57-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="7ff57-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7ff57-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7ff57-110">系数，后跟倒副本</span><span class="sxs-lookup"><span data-stu-id="7ff57-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="7ff57-111">示例</span><span class="sxs-lookup"><span data-stu-id="7ff57-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```