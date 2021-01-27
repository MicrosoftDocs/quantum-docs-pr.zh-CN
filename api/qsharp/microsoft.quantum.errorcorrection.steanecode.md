---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853057"
---
# <a name="steanecode-function"></a>SteaneCode 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个 CSS 值，它表示⟦7，1，3⟧ Steane 代码编码器，并使用就地的症状度量来表示解码器。

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>输出： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

CSS 类型的一个对象，该对象收集所有相关数据，以便对⟦7、1、3⟧ Steane 代码执行编码和错误更正。

## <a name="remarks"></a>备注

此代码在以下文章中找到：

- A. Steane，"多粒子干扰和量程错误纠正"，过程。 Roy. Lond。 A452 (1996) pp 2551; https://arxiv.org/abs/quant-ph/9601029.