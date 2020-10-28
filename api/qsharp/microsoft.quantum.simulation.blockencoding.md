---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700344"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="4ed89-102">BlockEncoding 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="4ed89-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="4ed89-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4ed89-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4ed89-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ed89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ed89-105">表示从左上方的块对任意相关运算符进行编码的单一项。</span><span class="sxs-lookup"><span data-stu-id="4ed89-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="4ed89-106">也就是说，是一个 `BlockEncoding` 单一 $U $，其中对系统寄存器操作的任意运算符 $H $ `s` 是在与辅助状态 $ \ket _a $ 对应的左上块中进行编码 {0} 。</span><span class="sxs-lookup"><span data-stu-id="4ed89-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="4ed89-107">即：</span><span class="sxs-lookup"><span data-stu-id="4ed89-107">That is,</span></span>

<span data-ttu-id="4ed89-108">$ $ \begin{align} ( \bra {0} _a \otimes I_s) U ( \ket {0} _a \otimes I_s) = H \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="4ed89-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

