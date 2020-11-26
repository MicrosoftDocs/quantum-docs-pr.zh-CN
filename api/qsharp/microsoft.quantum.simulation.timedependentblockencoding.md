---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TimeDependentBlockEncoding 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: 8fade22dca7af16a567a88f4413c8e9dcc1604b2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203495"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="c7cf5-102">TimeDependentBlockEncoding 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="c7cf5-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="c7cf5-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c7cf5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c7cf5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c7cf5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c7cf5-105">表示 `BlockEncoding` 由时钟寄存器控制的。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="c7cf5-106">也就是说，是一种 `TimeDependentBlockEncoding` 由状态 $ \ket{k} _d $ 在时钟寄存器中控制的单一 $U $， `d` 这样，在系统寄存器上操作的任意 $H _k $ 就 `s` 会在对应于辅助状态 $ \ket _a $ 的左上块中进行编码 {0} 。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="c7cf5-107">即：</span><span class="sxs-lookup"><span data-stu-id="c7cf5-107">That is,</span></span>

<span data-ttu-id="c7cf5-108">$ $ \begin{align} ( \bra {0} \_ a\otimes I_ {ds} ) U ( \ket {0} \_ a\otimes I_ {ds} ) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="c7cf5-109">\end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

