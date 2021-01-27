---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852153"
---
# <a name="snd-function"></a>Snd 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果给定对，则返回第二个元素。

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a>输入

### <a name="pair--tu"></a>配对： ( ' U) 

具有两个元素的元组。



## <a name="output--u"></a>输出： U

的第二个元素 `pair` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

对的第一个成员的类型。
### <a name="u"></a>' U

对的第二个成员的类型。