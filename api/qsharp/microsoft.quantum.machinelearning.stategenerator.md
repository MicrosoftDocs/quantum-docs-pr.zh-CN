---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700260"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


描述为顺序分类器准备给定输入的操作。

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>命名项

### <a name="nqubits--int"></a>NQubits： [Int](xref:microsoft.quantum.lang-ref.int)

在其上定义编码输入的 qubits 的数目。
### <a name="prepare--littleendian--unit-adj--ctl"></a>准备： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

一种操作，用于在 qubits 的小 endian 寄存器上准备编码的输入 `NQubits` 。