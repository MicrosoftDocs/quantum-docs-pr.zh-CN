---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 75fdbf13cf07d906982d4a611d1d25b3e29db2cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225425"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="a79c0-102">BlockEncoding 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="a79c0-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="a79c0-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a79c0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a79c0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a79c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a79c0-105">表示从左上方的块对任意相关运算符进行编码的单一项。</span><span class="sxs-lookup"><span data-stu-id="a79c0-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="a79c0-106">也就是说，是一个 `BlockEncoding` 单一 $U $，其中对系统寄存器操作的任意运算符 $H $ `s` 是在与辅助状态 $ \ket _a $ 对应的左上块中进行编码 {0} 。</span><span class="sxs-lookup"><span data-stu-id="a79c0-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="a79c0-107">即：</span><span class="sxs-lookup"><span data-stu-id="a79c0-107">That is,</span></span>

<span data-ttu-id="a79c0-108">$ $ \begin{align} ( \bra {0} _a \otimes I_s) U ( \ket {0} _a \otimes I_s) = H \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="a79c0-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

