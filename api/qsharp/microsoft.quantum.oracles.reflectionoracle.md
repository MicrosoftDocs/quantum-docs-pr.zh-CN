---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226649"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="9d09d-102">ReflectionOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="9d09d-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="9d09d-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9d09d-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9d09d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d09d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d09d-105">表示 oracle 反射。</span><span class="sxs-lookup"><span data-stu-id="9d09d-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="9d09d-106">反射 oracle $O $，具有输入：</span><span class="sxs-lookup"><span data-stu-id="9d09d-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="9d09d-107">用于旋转反射子空间的阶段 $ \phi $。</span><span class="sxs-lookup"><span data-stu-id="9d09d-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="9d09d-108">要对其执行给定反射的 qubit 注册。</span><span class="sxs-lookup"><span data-stu-id="9d09d-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="9d09d-109">命名项</span><span class="sxs-lookup"><span data-stu-id="9d09d-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="9d09d-110">ApplyReflection： ([Double](xref:microsoft.quantum.lang-ref.double)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9d09d-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="9d09d-111">备注</span><span class="sxs-lookup"><span data-stu-id="9d09d-111">Remarks</span></span>

<span data-ttu-id="9d09d-112">此 oracle $O = \boldone- (1-e ^ {i \phi} ) \ket{\psi}\bra{\psi} $ 对单个纯状态 $ \ket{\psi} $ 执行部分反射。</span><span class="sxs-lookup"><span data-stu-id="9d09d-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>