---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701145"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="17b61-102">MCMTMask 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="17b61-102">MCMTMask user defined type</span></span>

<span data-ttu-id="17b61-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="17b61-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="17b61-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17b61-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17b61-105">一种类型，用于表示多受控多目标 Toffoli 入口。</span><span class="sxs-lookup"><span data-stu-id="17b61-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="17b61-106">第一个整数是控件行的位掩码。</span><span class="sxs-lookup"><span data-stu-id="17b61-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="17b61-107">设置对应于控件行索引的位索引。</span><span class="sxs-lookup"><span data-stu-id="17b61-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="17b61-108">第二个整数是目标行的位掩码。</span><span class="sxs-lookup"><span data-stu-id="17b61-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="17b61-109">设置对应于目标行索引的位索引。</span><span class="sxs-lookup"><span data-stu-id="17b61-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="17b61-110">这两个整数的位索引必须是不连续的。</span><span class="sxs-lookup"><span data-stu-id="17b61-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="17b61-111">命名项</span><span class="sxs-lookup"><span data-stu-id="17b61-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="17b61-112">ControlMask： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17b61-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="17b61-113">TargetMask： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17b61-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>
