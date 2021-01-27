---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853691"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


如果获得成功概率，则返回一个在给定概率下为 true 的单个伯努利试用期。

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>输入

### <a name="successprobability--double"></a>successProbability： [Double](xref:microsoft.quantum.lang-ref.double)

应返回的概率 `true` 。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 具有概率 `successProbability` 和 `false` 有概率的 `1.0 - successProbability` 。

## <a name="example"></a>示例

以下 Q # 代码段示例从偏向硬币上翻：

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```