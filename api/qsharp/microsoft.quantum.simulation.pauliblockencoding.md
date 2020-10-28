---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696680"
---
# <a name="pauliblockencoding-function"></a>PauliBlockEncoding 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


为 Hamiltonian 创建块编码单一编码。

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ 由 $P $ _j $ 的 Pauli 术语的总和进行描述，每个术语都包含实系数 $ \ alpha_j $。

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>输入

### <a name="generatorsystem--generatorsystem"></a>generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

一个 `GeneratorSystem` ，它描述 $H $ 作为 Pauli 条款的总和



## <a name="output--doubleblockencodingreflection"></a>输出： ([Double](xref:microsoft.quantum.lang-ref.double)、[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)) 

## <a name="first-parameter"></a>第一个参数

系数 $ \alpha = \ sum_ {j} | \ alpha_j | $ 的一个标准。

## <a name="second-parameter"></a>第二个参数

`BlockEncodingReflection`Hamiltonian 的单一 $U $ $H $。 由于这个单一的 $U ^ 2 = I $，它也是一个反射。

## <a name="remarks"></a>注解

这是通过以下方法获取的：准备并 unpreparing 状态 $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $，并构造一个按乘法控制的单一 <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> 和 <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> 。