---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: efb820411be63352fc09ada2441a9140dd5575f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840241"
---
# <a name="repeatc-operation"></a>RepeatC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在给定的次数后重复操作。

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a>输入

### <a name="op--tinput--unit--is-ctl"></a>op： ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

要重复调用的操作。


### <a name="ntimes--int"></a>nTimes： [Int](xref:microsoft.quantum.lang-ref.int)

要调用的次数 `op` 。


### <a name="input--tinput"></a>输入： ' TInput

要传递到的输入 `op` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="tinput"></a>'TInput



## <a name="example"></a>示例

以下项是等效的：

```qsharp
RepeatC(U, 17, target);
(BoundC(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>另请参阅

- [DrawMany。](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Canon。重复](xref:Microsoft.Quantum.Canon.Repeat)
- [Canon. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)