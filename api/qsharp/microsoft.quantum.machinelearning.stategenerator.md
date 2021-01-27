---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854878"
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