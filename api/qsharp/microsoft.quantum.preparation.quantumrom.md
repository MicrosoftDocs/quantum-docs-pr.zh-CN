---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229879"
---
# <a name="quantumrom-function"></a>QuantumROM 函数

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROM 已被弃用。 请改用 <xref:Microsoft.Quantum.Preparation.PurifiedMixedState>。

使用量程 ROM 技术来表示给定的密度矩阵。

给定一个 $N $ 系数 $ \ alpha_j $ 的列表，这将返回一个单一 $U $，该类型使用量程方法为密度矩阵 $ \rho = \ p_j {j = 0} ^ {N-1} \frac{的 purification {j = 0} ^ {sum_ \tilde\rho\} sum_ \ket{j}\bra{j} ${\ sum_k | \ alpha_k |}\ket{j}\bra{j} $。 在此近似中，错误 $ \epsilon $ 是： $ | p_j-\frac{| alpha_j |}{\ sum_k | \ alpha_k |} |\le \epsilon/N $ 和 $ \| \tilde\rho-\rho \| \le \epsilon $。 换句话说，$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ 票证 {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}。
\end{align} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>输入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目标错误 $ \epsilon $。


### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

$N $ 系数的数组，用于指定基础状态的概率。
负数 $-\ alpha_j $ 将被视为正 $ | \ alpha_j | $。



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a>输出： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int)) # A4，[Double](xref:microsoft.quantum.lang-ref.double)， ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl) 

## <a name="first-parameter"></a>第一个参数

一个元组， `(x,(y,z))` 其中 `x = y + z` 是所分配的 qubits 总数， `y` 是寄存器的 qubits 数 `LittleEndian` ， `z` 是垃圾 qubits 的数目。

## <a name="second-parameter"></a>第二个参数

系数数组的单规范 $ \ sum_j | \ alpha_j | $。

## <a name="third-parameter"></a>第三个参数

单一 $U $。

## <a name="references"></a>参考

- 通过线性线路编码的电子 Spectra，Ryan Babbush、Craig Gidney、Dominic Berry、Nathan Wiebe、Jarrod McClean、Alexandru 暗、奥斯汀 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662