---
uid: Microsoft.Quantum.Synthesis.Encoded
title: 编码函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855486"
---
# <a name="encoded-function"></a>编码函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


{1,-1}编码事实数据表

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>输入

### <a name="table--bool"></a>table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

事实数据表作为真值数组



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

作为整数数组的事实数据表 {1,-1}

## <a name="example"></a>示例

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```