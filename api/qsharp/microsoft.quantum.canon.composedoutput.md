---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840891"
---
# <a name="composedoutput-function"></a>ComposedOutput 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

