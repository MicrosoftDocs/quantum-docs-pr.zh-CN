---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700848"
---
# <a name="truthtablesfrompermutationfolder-function"></a>TruthTablesFromPermutationFolder 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


单个变量索引的分解逻辑

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>说明

这会获取当前状态并生成更新的排列，并可能添加受控入口的新函数。

## <a name="input"></a>输入

### <a name="numvars--int"></a>numVars： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>状态： [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>输出： [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

