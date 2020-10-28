---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700093"
---
# <a name="reflectionphases-user-defined-type"></a>ReflectionPhases 用户定义的类型

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

软件包 [](https://nuget.org/packages/)


振幅放大中部分反射序列的阶段。

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>命名项

### <a name="aboutstart--double"></a>AboutStart： [Double](xref:microsoft.quantum.lang-ref.double)[]

用于反射开始状态的阶段的数组。
### <a name="abouttarget--double"></a>AboutTarget： [Double](xref:microsoft.quantum.lang-ref.double)[]

用于反射目标状态的阶段的数组。

## <a name="remarks"></a>注解

这两个数组的长度必须相等。 请注意，在许多情况下，有关目标状态的开始状态和最后一阶段的第一阶段会引入全局阶段转换，并可能设置为 $0 $。