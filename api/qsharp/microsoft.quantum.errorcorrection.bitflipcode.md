---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 2d0b50bd2467fc01caacbbcb22f98c59a2d13922
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201217"
---
# <a name="bitflipcode-function"></a>BitFlipCode 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个 QECC 值，该值表示⟦3，1，1⟧位翻转代码编码器和解码器，并使用就地症状度量。

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>输出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

通过指定类型返回量程错误更正代码的实现 `QECC` 。