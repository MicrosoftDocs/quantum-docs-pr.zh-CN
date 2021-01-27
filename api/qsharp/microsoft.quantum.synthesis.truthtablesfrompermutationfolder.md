---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 881bb8e29d3d7761cc521837502ea79b0714b381
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855250"
---
# <a name="truthtablesfrompermutationfolder-function"></a>TruthTablesFromPermutationFolder 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

