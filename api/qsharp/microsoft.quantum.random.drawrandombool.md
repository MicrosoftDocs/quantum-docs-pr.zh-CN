---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696690"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)

软件包 [](https://nuget.org/packages/)


如果获得成功概率，则返回一个在给定概率下为 true 的单个伯努利试用期。

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>输入

### <a name="successprobability--double"></a>successProbability： [Double](xref:microsoft.quantum.lang-ref.double)

应返回的概率 `true` 。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 具有概率 `successProbability` 和 `false` 有概率的 `1.0 - successProbability` 。