---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695504"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

软件包 [](https://nuget.org/packages/)


围绕 Y 轴旋转单个 qubit 乘以π/4。

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a>说明

执行关于的π/4 旋转 `Y` 。

旋转是通过使用神奇状态来执行的;也就是说，状态 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket 的副本 {8} {1} 。
\end{align} $ $

## <a name="input"></a>输入

### <a name="data--qubit"></a>数据： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要 $Y $ \pi/$4 旋转的 qubit。


### <a name="magic--qubit"></a>神奇： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

最初处于神奇状态的 qubit。 此操作的应用程序 `magic` 返回到 $ \ket {0} $ 状态。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

以下项是等效的：

```qsharp
Ry(PI() / 4.0, data);
```

和

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

此操作支持 `Adjoint` 函子，在这种情况下，使用的是相同的幻状态，但对数据 qubit 的影响是 $ \ pi/4 $ $Y $-旋转。