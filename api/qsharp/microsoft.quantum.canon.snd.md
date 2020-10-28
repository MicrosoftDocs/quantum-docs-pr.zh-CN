---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695951"
---
# <a name="snd-function"></a>Snd 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


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