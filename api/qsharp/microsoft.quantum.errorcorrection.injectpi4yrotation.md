---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825946"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation 操作

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


围绕 Y 轴旋转单个 qubit 乘以π/4。

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
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



## <a name="remarks"></a>备注

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