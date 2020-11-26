---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211553"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


描述为顺序分类器准备给定输入的操作。

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>命名项

### <a name="nqubits--int"></a>NQubits： [Int](xref:microsoft.quantum.lang-ref.int)

在其上定义编码输入的 qubits 的数目。
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>准备： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

一种操作，用于在 qubits 的小 endian 寄存器上准备编码的输入 `NQubits` 。