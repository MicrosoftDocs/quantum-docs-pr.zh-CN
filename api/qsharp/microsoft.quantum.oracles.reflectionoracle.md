---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854490"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="4f691-102">ReflectionOracle 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="4f691-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="4f691-103">命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="4f691-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="4f691-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f691-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f691-105">表示 oracle 反射。</span><span class="sxs-lookup"><span data-stu-id="4f691-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="4f691-106">反射 oracle $O $，具有输入：</span><span class="sxs-lookup"><span data-stu-id="4f691-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="4f691-107">用于旋转反射子空间的阶段 $ \phi $。</span><span class="sxs-lookup"><span data-stu-id="4f691-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="4f691-108">要对其执行给定反射的 qubit 注册。</span><span class="sxs-lookup"><span data-stu-id="4f691-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="4f691-109">命名项</span><span class="sxs-lookup"><span data-stu-id="4f691-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="4f691-110">ApplyReflection： ([Double](xref:microsoft.quantum.lang-ref.double)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="4f691-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="4f691-111">备注</span><span class="sxs-lookup"><span data-stu-id="4f691-111">Remarks</span></span>

<span data-ttu-id="4f691-112">此 oracle $O = \boldone- (1-e ^ {i \phi} ) \ket{\psi}\bra{\psi} $ 对单个纯状态 $ \ket{\psi} $ 执行部分反射。</span><span class="sxs-lookup"><span data-stu-id="4f691-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>