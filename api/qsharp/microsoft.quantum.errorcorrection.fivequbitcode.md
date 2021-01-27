---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853138"
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