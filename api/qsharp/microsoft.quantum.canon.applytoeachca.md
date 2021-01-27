---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: c85b33760eba8d10d9650be2f8306e4afdd1f307
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841488"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="b898c-102">ApplyToEachCA 操作</span><span class="sxs-lookup"><span data-stu-id="b898c-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="b898c-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b898c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b898c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b898c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b898c-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="b898c-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="b898c-106">修饰符 `CA` 指示 qubit 操作可控制和 adjointable。</span><span class="sxs-lookup"><span data-stu-id="b898c-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b898c-107">输入</span><span class="sxs-lookup"><span data-stu-id="b898c-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="b898c-108">singleElementOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b898c-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b898c-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="b898c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="b898c-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="b898c-110">register : 'T[]</span></span>

<span data-ttu-id="b898c-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="b898c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b898c-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b898c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b898c-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="b898c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b898c-114">找</span><span class="sxs-lookup"><span data-stu-id="b898c-114">'T</span></span>

<span data-ttu-id="b898c-115">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="b898c-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="b898c-116">示例</span><span class="sxs-lookup"><span data-stu-id="b898c-116">Example</span></span>

<span data-ttu-id="b898c-117">准备 qubit $ \ket{+} $ 状态：</span><span class="sxs-lookup"><span data-stu-id="b898c-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="b898c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b898c-118">See Also</span></span>

- [<span data-ttu-id="b898c-119">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="b898c-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)