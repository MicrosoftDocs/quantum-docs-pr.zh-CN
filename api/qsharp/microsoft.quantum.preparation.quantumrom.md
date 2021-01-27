---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 64ed9aed7c9d9a4a689c5926f3cd085a2521c4db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856824"
---
# <a name="quantumrom-function"></a><span data-ttu-id="6de10-102">QuantumROM 函数</span><span class="sxs-lookup"><span data-stu-id="6de10-102">QuantumROM function</span></span>

<span data-ttu-id="6de10-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6de10-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6de10-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6de10-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="6de10-105">QuantumROM 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="6de10-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="6de10-106">请改用 <xref:Microsoft.Quantum.Preparation.PurifiedMixedState>。</span><span class="sxs-lookup"><span data-stu-id="6de10-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="6de10-107">使用量程 ROM 技术来表示给定的密度矩阵。</span><span class="sxs-lookup"><span data-stu-id="6de10-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="6de10-108">给定一个 $N $ 系数 $ \ alpha_j $ 的列表，这将返回一个单一 $U $，该类型使用量程方法为密度矩阵 $ \rho = \ p_j {j = 0} ^ {N-1} \frac{的 purification {j = 0} ^ {sum_ \tilde\rho\} sum_ \ket{j}\bra{j} ${\ sum_k | \ alpha_k |}\ket{j}\bra{j} $。</span><span class="sxs-lookup"><span data-stu-id="6de10-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="6de10-109">在此近似中，错误 $ \epsilon $ 是： $ | p_j-\frac{| alpha_j |}{\ sum_k | \ alpha_k |} |\le \epsilon/N $ 和 $ \| \tilde\rho-\rho \| \le \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="6de10-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="6de10-110">换句话说，$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ 票证 {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}。</span><span class="sxs-lookup"><span data-stu-id="6de10-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="6de10-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="6de10-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="6de10-112">输入</span><span class="sxs-lookup"><span data-stu-id="6de10-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="6de10-113">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6de10-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6de10-114">目标错误 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="6de10-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="6de10-115">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6de10-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6de10-116">$N $ 系数的数组，用于指定基础状态的概率。</span><span class="sxs-lookup"><span data-stu-id="6de10-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="6de10-117">负数 $-\ alpha_j $ 将被视为正 $ | \ alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="6de10-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="6de10-118">输出： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int)) # A4，[Double](xref:microsoft.quantum.lang-ref.double)， ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="6de10-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="6de10-119">第一个参数</span><span class="sxs-lookup"><span data-stu-id="6de10-119">First parameter</span></span>

<span data-ttu-id="6de10-120">一个元组， `(x,(y,z))` 其中 `x = y + z` 是所分配的 qubits 总数， `y` 是寄存器的 qubits 数 `LittleEndian` ， `z` 是垃圾 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="6de10-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="6de10-121">第二个参数</span><span class="sxs-lookup"><span data-stu-id="6de10-121">Second parameter</span></span>

<span data-ttu-id="6de10-122">系数数组的单规范 $ \ sum_j | \ alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="6de10-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="6de10-123">第三个参数</span><span class="sxs-lookup"><span data-stu-id="6de10-123">Third parameter</span></span>

<span data-ttu-id="6de10-124">单一 $U $。</span><span class="sxs-lookup"><span data-stu-id="6de10-124">The unitary $U$.</span></span>

## <a name="example"></a><span data-ttu-id="6de10-125">示例</span><span class="sxs-lookup"><span data-stu-id="6de10-125">Example</span></span>

<span data-ttu-id="6de10-126">下面的代码段准备了 $ 3 $-qubit state $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} 的 purification{\ sum_k | \ alpha_k |}\ket{j}\bra{j} $，其中 $ \vec\alpha = (1.0，2.0，3.0，4.0，5.0) $，错误为 `1e-3` ;</span><span class="sxs-lookup"><span data-stu-id="6de10-126">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0,2.0,3.0,4.0,5.0)$, and the error is `1e-3`;</span></span>

```qsharp
let coefficients = [1.0,2.0,3.0,4.0,5.0];
let targetError = 1e-3;
let ((nTotalQubits, (nIndexQubits, nGarbageQubits)), oneNorm, op) = QuantumROM(targetError, coefficients);
using (indexRegister = Qubit[nIndexQubits]) {
    using (garbageRegister = Qubit[nGarbageQubits]) {
        op(LittleEndian(indexRegister), garbageRegister);
    }
}
```

## <a name="references"></a><span data-ttu-id="6de10-127">参考</span><span class="sxs-lookup"><span data-stu-id="6de10-127">References</span></span>

- <span data-ttu-id="6de10-128">通过线性线路编码的电子 Spectra，Ryan Babbush、Craig Gidney、Dominic Berry、Nathan Wiebe、Jarrod McClean、Alexandru 暗、奥斯汀 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="6de10-128">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>