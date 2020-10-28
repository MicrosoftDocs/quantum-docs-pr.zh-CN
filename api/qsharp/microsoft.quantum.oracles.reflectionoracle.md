---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700777"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle 用户定义的类型

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

软件包 [](https://nuget.org/packages/)


表示 oracle 反射。

反射 oracle $O $，具有输入：

- 用于旋转反射子空间的阶段 $ \phi $。
- 要对其执行给定反射的 qubit 注册。

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>命名项

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection： ([Double](xref:microsoft.quantum.lang-ref.double)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl



## <a name="remarks"></a>注解

此 oracle $O = \boldone- (1-e ^ {i \phi} ) \ket{\psi}\bra{\psi} $ 对单个纯状态 $ \ket{\psi} $ 执行部分反射。