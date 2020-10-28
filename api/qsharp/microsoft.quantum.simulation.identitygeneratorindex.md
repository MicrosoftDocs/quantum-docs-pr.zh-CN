---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700872"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


返回与零 Hamiltonian （与 `H = 0` 标识演化操作相对应）一致的生成器索引。

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>输入

### <a name="idxterm--int"></a>idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)

此输入将被忽略，并定义为与 <xref:microsoft.quantum.simulation.generatorsystem> 用户定义的类型保持一致。



## <a name="output--generatorindex"></a>输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

表示 Hamiltonian $H = $0 下的演变的生成器索引。