---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696539"
---
# <a name="drawmany-operation"></a>DrawMany 操作

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


对给定数量的样本重复操作，并在数组中收集其输出。

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>输入

### <a name="op--tinput--toutput"></a>op： ' TInput => ' TOutput 

要重复调用的操作。


### <a name="nsamples--int"></a>nSamples： [Int](xref:microsoft.quantum.lang-ref.int)

要收集的调用的示例数 `op` 。


### <a name="input--tinput"></a>输入： ' TInput

要传递到的输入 `op` 。



## <a name="output--toutput"></a>输出： "TOutput []



## <a name="type-parameters"></a>类型参数

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="see-also"></a>另请参阅

- [Canon。重复](xref:Microsoft.Quantum.Canon.Repeat)