---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695566"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="f0278-102">EqualityFactL 函数</span><span class="sxs-lookup"><span data-stu-id="f0278-102">EqualityFactL function</span></span>

<span data-ttu-id="f0278-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f0278-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f0278-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0278-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0278-105">断言传统 BigInt 变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="f0278-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="f0278-106">输入</span><span class="sxs-lookup"><span data-stu-id="f0278-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="f0278-107">实际： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f0278-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f0278-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="f0278-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="f0278-109">应为： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f0278-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f0278-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="f0278-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="f0278-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f0278-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f0278-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="f0278-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0278-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0278-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

