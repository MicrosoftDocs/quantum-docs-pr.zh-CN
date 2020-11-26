---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203004"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


一种类型，用于表示多受控多目标 Toffoli 入口。

第一个整数是控件行的位掩码。  设置对应于控件行索引的位索引。

第二个整数是目标行的位掩码。  设置对应于目标行索引的位索引。

这两个整数的位索引必须是不连续的。

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>命名项

### <a name="controlmask--int"></a>ControlMask： [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask： [Int](xref:microsoft.quantum.lang-ref.int)

