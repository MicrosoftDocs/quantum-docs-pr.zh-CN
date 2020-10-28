---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695504"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="23105-102">InjectPi4YRotation 操作</span><span class="sxs-lookup"><span data-stu-id="23105-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="23105-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="23105-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="23105-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23105-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23105-105">围绕 Y 轴旋转单个 qubit 乘以π/4。</span><span class="sxs-lookup"><span data-stu-id="23105-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="23105-106">说明</span><span class="sxs-lookup"><span data-stu-id="23105-106">Description</span></span>

<span data-ttu-id="23105-107">执行关于的π/4 旋转 `Y` 。</span><span class="sxs-lookup"><span data-stu-id="23105-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="23105-108">旋转是通过使用神奇状态来执行的;也就是说，状态 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket 的副本 {8} {1} 。</span><span class="sxs-lookup"><span data-stu-id="23105-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="23105-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="23105-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="23105-110">输入</span><span class="sxs-lookup"><span data-stu-id="23105-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="23105-111">数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="23105-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="23105-112">要 $Y $ \pi/$4 旋转的 qubit。</span><span class="sxs-lookup"><span data-stu-id="23105-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="23105-113">神奇： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="23105-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="23105-114">最初处于神奇状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="23105-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="23105-115">此操作的应用程序 `magic` 返回到 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="23105-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="23105-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23105-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="23105-117">注解</span><span class="sxs-lookup"><span data-stu-id="23105-117">Remarks</span></span>

<span data-ttu-id="23105-118">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="23105-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="23105-119">和</span><span class="sxs-lookup"><span data-stu-id="23105-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="23105-120">此操作支持 `Adjoint` 函子，在这种情况下，使用的是相同的幻状态，但对数据 qubit 的影响是 $ \ pi/4 $ $Y $-旋转。</span><span class="sxs-lookup"><span data-stu-id="23105-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>