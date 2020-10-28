---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696099"
---
# <a name="composedoutput-function"></a>ComposedOutput 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


返回给定输入的和的组合的输出 `inner` `outer` 。

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>输入

### <a name="outer--u---v"></a>外部： "U->" V




### <a name="inner--t---u"></a>内部：不 > "U




### <a name="target--t"></a>目标： t





## <a name="output--v"></a>输出： "V



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找


### <a name="u"></a>' U


### <a name="v"></a>' V

