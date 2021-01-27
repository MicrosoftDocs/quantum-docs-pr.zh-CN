---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855528"
---
# <a name="decomposedon-function"></a>DecomposedOn 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对变量分解

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>说明

给定排列 $ \pi $ (`perm`) ，$i $ () 的索引 `index` ，此方法返回三个排列 $ ( # A5 \ pi_l，\ pi_r) ，\pi ' ) $，以使 $ \ pi_l $ 和 $ \ pi_r $ 的图像不会在其元素中的索引（而不是 $ \pi ' $ 的）中更改其元素中的位。

## <a name="input"></a>输入

### <a name="perm--int"></a>永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)[]，[int](xref:microsoft.quantum.lang-ref.int)[] ) ，[int](xref:microsoft.quantum.lang-ref.int)[] ) 



## <a name="example"></a>示例

假设输入为永久状态 = [0，2，3，5，7，1，4，6]，index = 0，则此函数将基于下表计算三个排列，其中 `perm` 使用组 A 中的元素和组 D 中的图像列出二进制表示法中的排列。 列列出位索引。

|  A |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

索引的所有值不等于 0 (= 索引) 从 A 复制到 B，从 D 复制到 C。

|  A |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

接下来，将在块 B 中第0列处为第一个具有空索引的元素放置0，然后将1放置在 B 中，其中前缀与索引 0 0) 的其他行 (。
之后，在块 C 的同一行中添加一个1，然后在块 C 中将相应的前缀添加为0。 重复此过程，直到所有索引都放置在块 B 和 C 的第0列中。

|  A |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

我们可以从表中读取三个新排列：

- $ \ pi_l $ 包含中的元素，B (左的图像) 
- $ \ pi_r $ with D 中的元素，C 中的图像 (right) 
- $ \pi $ with B 中的元素，C 中的图像 (余数) 

请注意，按设计位值不会更改索引1和2的 $ \ pi_l $ 和 $ \ pi_r $，并且索引0的 $ \ pi_ $ $ 中的位值不会发生更改。  另请注意，$ \ pi_l $ 和 $ \ pi_r $ 必须是自反的。

派生的和返回的排列包括： left = [0，1，2，3，4，5，6，7] right = [0，1，3，2，4，5，7，6] 余数 = [0，3，2，5，6，1，4，7]