---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TimeDependentBlockEncoding 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: e2b191a4fc44f99c88f25da9b1ee6460d936740b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814261"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="6347f-102">TimeDependentBlockEncoding 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="6347f-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="6347f-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6347f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6347f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6347f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6347f-105">表示 `BlockEncoding` 由时钟寄存器控制的。</span><span class="sxs-lookup"><span data-stu-id="6347f-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="6347f-106">也就是说，是一种 `TimeDependentBlockEncoding` 由状态 $ \ket{k} _d $ 在时钟寄存器中控制的单一 $U $， `d` 这样，在系统寄存器上操作的任意 $H _k $ 就 `s` 会在对应于辅助状态 $ \ket _a $ 的左上块中进行编码 {0} 。</span><span class="sxs-lookup"><span data-stu-id="6347f-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="6347f-107">即：</span><span class="sxs-lookup"><span data-stu-id="6347f-107">That is,</span></span>

<span data-ttu-id="6347f-108">$ $ \begin{align} ( \bra {0} \_ a\otimes I_ {ds} ) U ( \ket {0} \_ a\otimes I_ {ds} ) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k。</span><span class="sxs-lookup"><span data-stu-id="6347f-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="6347f-109">\end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="6347f-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

