---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224711"
---
# <a name="selectz-operation"></a><span data-ttu-id="44997-102">SelectZ 操作</span><span class="sxs-lookup"><span data-stu-id="44997-102">SelectZ operation</span></span>

<span data-ttu-id="44997-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="44997-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="44997-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="44997-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="44997-105">一种单一 $U $，它对索引状态 $ \ket{p} $ $p 上 $Z 的 qubits $</span><span class="sxs-lookup"><span data-stu-id="44997-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="44997-106">也就是说，$ $ \begin{align} U\ket {p} \ 票证 {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="44997-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="44997-107">输入</span><span class="sxs-lookup"><span data-stu-id="44997-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="44997-108">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="44997-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="44997-109">此寄存器的状态 $ \ket{p} $ 确定应用 $Z $ 的 qubit。</span><span class="sxs-lookup"><span data-stu-id="44997-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="44997-110">targetRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="44997-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="44997-111">注册应用 Pauli 运算符的 qubits。</span><span class="sxs-lookup"><span data-stu-id="44997-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44997-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44997-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

