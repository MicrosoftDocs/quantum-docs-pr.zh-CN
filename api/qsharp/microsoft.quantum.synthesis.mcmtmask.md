---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855377"
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

