---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695731"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="38d2a-102">OptimizedBEXY 操作</span><span class="sxs-lookup"><span data-stu-id="38d2a-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="38d2a-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="38d2a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="38d2a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38d2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38d2a-105">一个单一 $U $，适用于 $ (X ^ {z + 1} \_ pY ^ {z} \_ p) z \_ {p-1} .。。在索引 $z \in \{ 0、1 \} $ 和 $p $ 上 Z_0 $ $。</span><span class="sxs-lookup"><span data-stu-id="38d2a-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="38d2a-106">也就是说，$ $ \begin{align} U\ket {z} \ 票证 {p} \ 票证 {\ psi} = \ket{z}\ket{p} (X ^ {z + 1} \_ pY ^ {z} \_ p) z \_ {p-1} .。。Z_0 \ket{\psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="38d2a-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="38d2a-107">输入</span><span class="sxs-lookup"><span data-stu-id="38d2a-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="38d2a-108">pauliBasis： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="38d2a-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="38d2a-109">如果此 qubit 处于状态 $ \ket {0} $，则应用 $X $。</span><span class="sxs-lookup"><span data-stu-id="38d2a-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="38d2a-110">当它处于状态 $ \ket {1} $ 时，应用 $Y $。</span><span class="sxs-lookup"><span data-stu-id="38d2a-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="38d2a-111">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="38d2a-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="38d2a-112">此寄存器的状态 $ \ket{p} $ 确定应用 $X $ 或 $Y $ 的 qubit。</span><span class="sxs-lookup"><span data-stu-id="38d2a-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="38d2a-113">targetRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="38d2a-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="38d2a-114">注册应用 Pauli 运算符的 qubits。</span><span class="sxs-lookup"><span data-stu-id="38d2a-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38d2a-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38d2a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="38d2a-116">参考</span><span class="sxs-lookup"><span data-stu-id="38d2a-116">References</span></span>

- <span data-ttu-id="38d2a-117">通过线性线路编码的电子 Spectra，Ryan Babbush、Craig Gidney、Dominic Berry、Nathan Wiebe、Jarrod McClean、Alexandru 暗、奥斯汀 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="38d2a-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>