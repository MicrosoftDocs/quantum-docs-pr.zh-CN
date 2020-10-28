---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695967"
---
# <a name="repeata-operation"></a>RepeatA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


在给定的次数后重复操作。

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>输入

### <a name="op--tinput--unit-adj"></a>op： ' TInput => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

要重复调用的操作。


### <a name="ntimes--int"></a>nTimes： [Int](xref:microsoft.quantum.lang-ref.int)

要调用的次数 `op` 。


### <a name="input--tinput"></a>输入： ' TInput

要传递到的输入 `op` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="tinput"></a>'TInput



## <a name="see-also"></a>另请参阅

- [DrawMany。](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Canon。重复](xref:Microsoft.Quantum.Canon.Repeat)
- [Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)