---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: dacc52766cf72d2bd562b76fc4939f962133e9a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700009"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="f196a-102">ApplyPhaseLEOperationOnLE 操作</span><span class="sxs-lookup"><span data-stu-id="f196a-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="f196a-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f196a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f196a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f196a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f196a-105">应用一个 <xref:microsoft.quantum.arithmetic.littleendian> 在类型为的目标寄存器上采用注册为输入的操作 <xref:microsoft.quantum.arithmetic.phaselittleendian> 。</span><span class="sxs-lookup"><span data-stu-id="f196a-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="f196a-106">输入</span><span class="sxs-lookup"><span data-stu-id="f196a-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="f196a-107">op： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f196a-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f196a-108">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="f196a-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="f196a-109">目标： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f196a-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f196a-110">要向其应用操作的寄存器。</span><span class="sxs-lookup"><span data-stu-id="f196a-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f196a-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f196a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f196a-112">注解</span><span class="sxs-lookup"><span data-stu-id="f196a-112">Remarks</span></span>

<span data-ttu-id="f196a-113">通过使用将寄存器转换为 `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ，然后在应用后将其返回到其原始表示形式 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f196a-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f196a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f196a-114">See Also</span></span>

- [<span data-ttu-id="f196a-115">Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="f196a-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="f196a-116">Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="f196a-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="f196a-117">Canon. ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="f196a-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)