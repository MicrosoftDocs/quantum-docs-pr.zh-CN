---
uid: Microsoft.Quantum.Canon.Repeat
title: 重复操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 40ee191e8d9044f33aa1621303c70f7e0847e8f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852245"
---
# <a name="repeat-operation"></a>重复操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在给定的次数后重复操作。

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>输入

### <a name="op--tinput--unit"></a>op： ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) 

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
Repeat(U, 17, target);
(Bound(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>另请参阅

- [DrawMany。](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Canon. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)