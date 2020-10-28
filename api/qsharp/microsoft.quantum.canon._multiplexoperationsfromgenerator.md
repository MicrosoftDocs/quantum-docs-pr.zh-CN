---
uid: Microsoft.Quantum.Canon._MultiplexOperationsFromGenerator
title: _MultiplexOperationsFromGenerator 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: _MultiplexOperationsFromGenerator
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 17d8f3e9b800e26a00969418ca061e3ea1d97682
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696395"
---
# <a name="_multiplexoperationsfromgenerator-operation"></a>_MultiplexOperationsFromGenerator 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


的实现步骤 `MultiplexOperationsFromGenerator` 。

```qsharp
operation _MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>输入

### <a name="unitarygenerator--intintint---t--unit-adj--ctl"></a>unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> = => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl) 




### <a name="auxiliary--qubit"></a>辅助： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>目标： t





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="see-also"></a>另请参阅

- [Canon. MultiplexOperationsFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)