---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695507"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

软件包 [](https://nuget.org/packages/)


返回一个 QECC 值，该值表示⟦5、1、3⟧代码编码器和解码器，并提供就地的症状度量。

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>输出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

通过指定类型返回量程错误更正代码的实现 `QECC` 。

## <a name="remarks"></a>注解

以下两篇文章中单独找到了此代码：

- C. H. Bennett，DiVincenzo，J。 Smolin 和 K. K。 Wootters，"混合状态牵连和量程错误更正" Phys，54 (1996) pp 3824-3851; https://arxiv.org/abs/quant-ph/9604024 和
- R. Laflamme，Miquel，J P。 巴斯和 W.x.y.z。 Zurek "完美的量程错误纠正代码" Phys Lett。 77 (1996) pp 198-201; https://arxiv.org/abs/quant-ph/9602019