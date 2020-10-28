---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701064"
---
# <a name="decompositionstate-user-defined-type"></a>DecompositionState 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


基于变量索引的分解过程中的状态

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a>命名项

### <a name="perm--int"></a>永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]


### <a name="lfunctions--bigintint"></a>Lfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []


### <a name="rfunctions--bigintint"></a>Rfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []



## <a name="description"></a>说明

状态包含当前排列和当前为控制的入口的当前生成的函数，右侧有控制的入口。