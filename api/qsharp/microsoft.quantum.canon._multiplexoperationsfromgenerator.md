---
uid: Microsoft.Quantum.Canon._MultiplexOperationsFromGenerator
title: _MultiplexOperationsFromGenerator 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: _MultiplexOperationsFromGenerator
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 17d8f3e9b800e26a00969418ca061e3ea1d97682
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696395"
---
# <a name="_multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="b1f5f-102">_MultiplexOperationsFromGenerator 操作</span><span class="sxs-lookup"><span data-stu-id="b1f5f-102">_MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="b1f5f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b1f5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b1f5f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1f5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1f5f-105">的实现步骤 `MultiplexOperationsFromGenerator` 。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-105">Implementation step of `MultiplexOperationsFromGenerator`.</span></span>

```qsharp
operation _MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="b1f5f-106">输入</span><span class="sxs-lookup"><span data-stu-id="b1f5f-106">Input</span></span>

### <a name="unitarygenerator--intintint---t--unit-adj--ctl"></a><span data-ttu-id="b1f5f-107">unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> = => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="b1f5f-107">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="b1f5f-108">辅助： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b1f5f-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="b1f5f-109">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b1f5f-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="b1f5f-110">目标： t</span><span class="sxs-lookup"><span data-stu-id="b1f5f-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="b1f5f-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1f5f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b1f5f-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="b1f5f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1f5f-113">找</span><span class="sxs-lookup"><span data-stu-id="b1f5f-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="b1f5f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1f5f-114">See Also</span></span>

- [<span data-ttu-id="b1f5f-115">Canon. MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="b1f5f-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)