---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200877"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个 QECC 值，该值表示⟦5、1、3⟧代码编码器和解码器，并提供就地的症状度量。

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>输出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

通过指定类型返回量程错误更正代码的实现 `QECC` 。

## <a name="remarks"></a>备注

以下两篇文章中单独找到了此代码：

- C. H. Bennett，DiVincenzo，J。 Smolin 和 K. K。 Wootters，"混合状态牵连和量程错误更正" Phys，54 (1996) pp 3824-3851; https://arxiv.org/abs/quant-ph/9604024 和
- R. Laflamme，Miquel，J P。 巴斯和 W.x.y.z。 Zurek "完美的量程错误纠正代码" Phys Lett。 77 (1996) pp 198-201; https://arxiv.org/abs/quant-ph/9602019