---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192955"
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