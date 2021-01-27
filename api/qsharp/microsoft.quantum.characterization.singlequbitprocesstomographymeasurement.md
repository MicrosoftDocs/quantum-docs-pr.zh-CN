---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839644"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>SingleQubitProcessTomographyMeasurement 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


根据感兴趣的特定通道，在 Pauli 基础上执行 qubit 进程 tomography 度量。

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>输入

### <a name="preparation--pauli"></a>准备： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli basis 元素 $P $，其中 qubit 准备就绪。


### <a name="measurement--pauli"></a>度量： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli 基础元素 $Q $，其中 qubit 将在其中进行度量。


### <a name="channel--qubit--unit"></a>频道： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [单元](xref:microsoft.quantum.lang-ref.unit) 

使用进程 tomography 估计其行为的单个 qubit 通道 $ \Lambda $。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__

概率为 `Zero` $ $ \Begin{align} \Pr ( \texttt{zero} | \Lambda; 的结果P，Q) = \operatorname{Tr}\left ( \frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right) 。
\end{align} $ $

## <a name="remarks"></a>备注

此操作返回的结果的分布是 qubit 状态 tomography 的一种特殊情况。 让 $ \rho = J ( \Lambda) /$2 作为 $ \Lambda $ 的 Choi – Jamiłkowski 状态。 然后，上面的分发与 $ $ \begin{align} \Pr ( \texttt{Zero} |rhoM) = \operatorname{Tr} (M \rho) ，\end{align} $ $，其中 $M = 2 ( \boldone + P) ^ \mathrm{T}/2 \cdot ( \boldone + Q) /$2 是对应于 $P $ 和 $Q $ 的有效度量值。