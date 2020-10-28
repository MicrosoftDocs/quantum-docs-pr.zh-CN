---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700420"
---
# <a name="quantumrom-function"></a><span data-ttu-id="b7525-102">QuantumROM 函数</span><span class="sxs-lookup"><span data-stu-id="b7525-102">QuantumROM function</span></span>

<span data-ttu-id="b7525-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b7525-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b7525-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7525-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7525-105">使用量程 ROM 技术来表示给定的密度矩阵。</span><span class="sxs-lookup"><span data-stu-id="b7525-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="b7525-106">给定一个 $N $ 系数 $ \ alpha_j $ 的列表，这将返回一个单一 $U $，该类型使用量程方法为密度矩阵 $ \rho = \ p_j {j = 0} ^ {N-1} \frac{的 purification {j = 0} ^ {sum_ \tilde\rho\} sum_ \ket{j}\bra{j} ${\ sum_k | \ alpha_k |}\ket{j}\bra{j} $。</span><span class="sxs-lookup"><span data-stu-id="b7525-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="b7525-107">在此近似中，错误 $ \epsilon $ 是： $ | p_j-\frac{| alpha_j |}{\ sum_k | \ alpha_k |} |\le \epsilon/N $ 和 $ \| \tilde\rho-\rho \| \le \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="b7525-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="b7525-108">换句话说，$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ 票证 {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}。</span><span class="sxs-lookup"><span data-stu-id="b7525-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="b7525-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b7525-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="b7525-110">输入</span><span class="sxs-lookup"><span data-stu-id="b7525-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="b7525-111">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7525-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7525-112">目标错误 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="b7525-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="b7525-113">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b7525-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b7525-114">$N $ 系数的数组，用于指定基础状态的概率。</span><span class="sxs-lookup"><span data-stu-id="b7525-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="b7525-115">负数 $-\ alpha_j $ 将被视为正 $ | \ alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="b7525-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="b7525-116">输出： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int)) # A4，[Double](xref:microsoft.quantum.lang-ref.double)， ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="b7525-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="b7525-117">第一个参数</span><span class="sxs-lookup"><span data-stu-id="b7525-117">First parameter</span></span>

<span data-ttu-id="b7525-118">一个元组， `(x,(y,z))` 其中 `x = y + z` 是所分配的 qubits 总数， `y` 是寄存器的 qubits 数 `LittleEndian` ， `z` 是垃圾 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="b7525-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="b7525-119">第二个参数</span><span class="sxs-lookup"><span data-stu-id="b7525-119">Second parameter</span></span>

<span data-ttu-id="b7525-120">系数数组的单规范 $ \ sum_j | \ alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="b7525-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="b7525-121">第三个参数</span><span class="sxs-lookup"><span data-stu-id="b7525-121">Third parameter</span></span>

<span data-ttu-id="b7525-122">单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="b7525-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="b7525-123">参考</span><span class="sxs-lookup"><span data-stu-id="b7525-123">References</span></span>

- <span data-ttu-id="b7525-124">通过线性线路编码的电子 Spectra，Ryan Babbush、Craig Gidney、Dominic Berry、Nathan Wiebe、Jarrod McClean、Alexandru 暗、奥斯汀 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="b7525-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>