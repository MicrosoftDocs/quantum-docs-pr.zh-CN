---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696701"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

软件包 [](https://nuget.org/packages/)


给定多 qubit Pauli 运算符的数组，使用指定的度量小工具测量每个运算符，然后返回结果的数组。

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>输入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

要测量的多 qubit Pauli 运算符的数组。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

进行注册以衡量给定运算符。


### <a name="gadget--pauliqubit--__invalidresult__"></a>小工具： ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]、 [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => __无效 <Result>__ 

执行给定多 qubit 运算符度量的操作。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__ []

从测量上的每个元素获得的结果的数组 `paulis` `target` 。