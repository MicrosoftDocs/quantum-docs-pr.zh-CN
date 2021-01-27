---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846205"
---
# <a name="drawmany-operation"></a>DrawMany 操作

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>示例

下面的示例为一个整数，给定一个操作，该操作一次采样一个位。

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>另请参阅

- [Canon。重复](xref:Microsoft.Quantum.Canon.Repeat)