---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856835"
---
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements 函数

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回必须分配的 qubits 总数，以应用返回的操作 @"microsoft.quantum.preparation.purifiedmixedstate" 。

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>输入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目标错误 $ \epsilon $。


### <a name="ncoefficients--int"></a>nCoefficients： [Int](xref:microsoft.quantum.lang-ref.int)

准备混合状态时要指定的系数数。



## <a name="output--mixedstatepreparationrequirements"></a>输出： [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

描述对每个函数所使用的 qubits 和每个索引和垃圾寄存器的总计 @"microsoft.quantum.preparation.purifiedmixedstate" 。

## <a name="see-also"></a>另请参阅

- [PurifiedMixedState。](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)