---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695484"
---
# <a name="steanecode-function"></a>SteaneCode 函数

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

软件包 [](https://nuget.org/packages/)


返回一个 CSS 值，它表示⟦7，1，3⟧ Steane 代码编码器，并使用就地的症状度量来表示解码器。

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>输出： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

CSS 类型的一个对象，该对象收集所有相关数据，以便对⟦7、1、3⟧ Steane 代码执行编码和错误更正。

## <a name="remarks"></a>注解

此代码在以下文章中找到：

- A. Steane，"多粒子干扰和量程错误纠正"，过程。 Roy. Lond。 A452 (1996) pp 2551; https://arxiv.org/abs/quant-ph/9601029.