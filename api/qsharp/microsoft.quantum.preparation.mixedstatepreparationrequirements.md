---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: MixedStatePreparationRequirements 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: 3ea4757f6aa5125418b1e81db9f32e7b668eb359
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228689"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a>MixedStatePreparationRequirements 用户定义的类型

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示准备给定混合状态所需的 qubits 的数目。

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a>命名项

### <a name="ntotalqubits--int"></a>NTotalQubits： [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="nindexqubits--int"></a>NIndexQubits： [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="ngarbagequbits--int"></a>NGarbageQubits： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="see-also"></a>另请参阅

- [PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)